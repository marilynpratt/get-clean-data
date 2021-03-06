#Getting and Cleaning Data, Peer Assessment Project


The script called: run_analysis.R downloads data collected from the accelerometers from the Samsung Galaxy S smartphone. 
A full description of the data is available at the site where the data was obtained: 
http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones 


This script does the following:

*STEP 1.	Merges the original training and the test sets to create one data set of 10,299 observations of 30 participants performing 6 activities over 561 variables.
*STEP 2.	Extracts only the measurements on the mean and standard deviation for each measurement reducing the variables to 86. 
*STEP 3.	Uses descriptive activity names to name the activities in the data set (see below)
*STEP 4.	Appropriately labels the data set with descriptive variable names(see variable names in CodeBook.md). 
*STEP 5.	Creates a second, independent tidy data set with the average of each variable for each activity and each subject.
*STEP 6.        Outputs a text file called Tidydata.txt

The script will create a tidy data set containing the means of all the columns per test participant and per each of six activities:
1 WALKING

2 WALKING_UPSTAIRS

3 WALKING_DOWNSTAIRS

4 SITTING

5 STANDING

6 LAYING
 

This tidy dataset will be written to a tab-delimited file called tidy.txt, which can also be found in this repository.

##STEP 1.	Merge the training and the test data sets to create one data set.

train <- read.table("UCI HAR Dataset/train/X_train.txt")
test <- read.table("UCI HAR Dataset/test/X_test.txt")
combined <- rbind(train, test)

##STEP 2.	Extract only the measurements on the mean and standard deviation for each measurement. 

featurenames <- read.table("UCI HAR Dataset/features.txt")
stdmean <- grep("std|mean|Mean", featurenames[,2])
dt <- data.frame(stdmean)
rows<-nrow(dt)
combined <-  combined[,stdmean]

##STEP 3. Use descriptive activity names to name the activities in the data set
##and STEP 4. Appropriately labels the data set with descriptive variable names

colnames(combined) <- featurenames[stdmean,2]
names(combined) <- gsub("^t", "Time", names(combined))
names(combined) <- gsub("^f", "Frequency", names(combined))
names(combined) <- gsub("-mean\\(\\)", "Mean", names(combined))
names(combined) <- gsub("Acc", "Accelerometer", names(combined))
names(combined) <- gsub("Gyro", "Gyroscope", names(combined))
names(combined) <- gsub("-std\\(\\)", "StdDev", names(combined))
names(combined) <- gsub("BodyBody", "Body", names(combined))
names(combined) <- gsub("()", "", names(combined))
names(combined) <- gsub("\\(", "", names(combined))
names(combined) <- gsub("\\)", "", names(combined))
names(combined) <- gsub(",", "-", names(combined))

### Read and combine the train and test activity codes
train.activity.codes <- read.table("UCI HAR Dataset/train/y_train.txt")
test.activity.codes <- read.table("UCI HAR Dataset/test/y_test.txt")
combined.activities <- rbind(train.activity.codes, test.activity.codes)
activity.labels <- read.table("UCI HAR Dataset/activity_labels.txt")
combined.activities$activity <- factor(combined.activities$V1, levels = activity.labels$V1, labels = activity.labels$V2)
colnames(activity.labels) <- c("activity code", "activity text")

### Get and combine the train and test subject ids
train.subjects <- read.table("UCI HAR Dataset/train/subject_train.txt")
test.subjects <- read.table("UCI HAR Dataset/test/subject_test.txt")
total.subjects <- rbind(train.subjects, test.subjects)

### Combine and name subjects and activity names
subjects.and.activities <- cbind(total.subjects, combined.activities$activity)
colnames(subjects.and.activities) <- c("Subjectid", "Activity")

### Combine with measures of means and standard deviation for resulting data frame
all <- cbind(subjects.and.activities, combined)

#Step 5.	Create tidy data set with the average of each variable for each activity and each subject.
tidydata <- aggregate(all[,3:rows], by = list(all$Subjectid, all$Activity), FUN = mean)
colnames(tidydata)[1:2] <- c("Subjectid", "Activity")
###sort by subject and activity
tidydata <- tidydata[order(tidydata$Subjectid, tidydata$Activity),]  
#STEP 6.    Output text file of Tidy Data
write.table(tidydata, file="Tidydata.txt", row.names = FALSE, col.names = TRUE)
check.tidy <- read.table("Tidydata.txt", header = TRUE)
titles <- colnames(tidydata)
write.table(titles, file="title.txt", row.names = FALSE, col.names = FALSE)
check.titles <- read.table("title.txt", header = FALSE)
