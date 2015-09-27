# Description

For the data used in this project, see the README.txt found in http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones. 
### Data set

**Subject**: the id of the volunteer that performed the activities wearing a smartphone on waist (1-30).

**Activity**: the activity the subject performed (values: 1-6; labels: WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING).

The other variables are the average of values (within a range -1, 1) representing the acquired smartphone signals. Their names are descriptive:

* '-XYZ' is used to denote 3-axial signals in the X, Y and Z directions;

* prefix 't' to denote time, 'f' frequency domain signals;

* variables from signals acquired from the accelerometer and gyroscope contains 'tAcc' and 'tGyro';

* the acceleration signal was separated into body and gravity acceleration signals ('tBodyAcc' and 'tGravityAcc');

* the body linear acceleration and angular velocity were derived in time to obtain Jerk signals  'tBodyAccJerk' and 'tBodyGyroJerk');

* the magnitude of these three-dimensional signals were calculated using the Euclidean norm (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag);

* a Fast Fourier Transform was applied to some of these signals producing fBodyAcc-XYZ, fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag.
 

### Variables (after cleaning 86 columns of Wide Data)
<pre>
Subjectid
Activity
TimeBodyAccelerometerMean-X
TimeBodyAccelerometerMean-Y
TimeBodyAccelerometerMean-Z
TimeBodyAccelerometerStdDev-X
TimeBodyAccelerometerStdDev-Y
TimeBodyAccelerometerStdDev-Z
TimeGravityAccelerometerMean-X
TimeGravityAccelerometerMean-Y
TimeGravityAccelerometerMean-Z
TimeGravityAccelerometerStdDev-X
TimeGravityAccelerometerStdDev-Y
TimeGravityAccelerometerStdDev-Z
TimeBodyAccelerometerJerkMean-X
TimeBodyAccelerometerJerkMean-Y
TimeBodyAccelerometerJerkMean-Z
TimeBodyAccelerometerJerkStdDev-X
TimeBodyAccelerometerJerkStdDev-Y
TimeBodyAccelerometerJerkStdDev-Z
TimeBodyGyroscopeMean-X
TimeBodyGyroscopeMean-Y
TimeBodyGyroscopeMean-Z
TimeBodyGyroscopeStdDev-X
TimeBodyGyroscopeStdDev-Y
TimeBodyGyroscopeStdDev-Z
TimeBodyGyroscopeJerkMean-X
TimeBodyGyroscopeJerkMean-Y
TimeBodyGyroscopeJerkMean-Z
TimeBodyGyroscopeJerkStdDev-X
TimeBodyGyroscopeJerkStdDev-Y
TimeBodyGyroscopeJerkStdDev-Z
TimeBodyAccelerometerMagMean
TimeBodyAccelerometerMagStdDev
TimeGravityAccelerometerMagMean
TimeGravityAccelerometerMagStdDev
TimeBodyAccelerometerJerkMagMean
TimeBodyAccelerometerJerkMagStdDev
TimeBodyGyroscopeMagMean
TimeBodyGyroscopeMagStdDev
TimeBodyGyroscopeJerkMagMean
TimeBodyGyroscopeJerkMagStdDev
FrequencyBodyAccelerometerMean-X
FrequencyBodyAccelerometerMean-Y
FrequencyBodyAccelerometerMean-Z
FrequencyBodyAccelerometerStdDev-X
FrequencyBodyAccelerometerStdDev-Y
FrequencyBodyAccelerometerStdDev-Z
FrequencyBodyAccelerometer-meanFreq-X
FrequencyBodyAccelerometer-meanFreq-Y
FrequencyBodyAccelerometer-meanFreq-Z
FrequencyBodyAccelerometerJerkMean-X
FrequencyBodyAccelerometerJerkMean-Y
FrequencyBodyAccelerometerJerkMean-Z
FrequencyBodyAccelerometerJerkStdDev-X
FrequencyBodyAccelerometerJerkStdDev-Y
FrequencyBodyAccelerometerJerkStdDev-Z
FrequencyBodyAccelerometerJerk-meanFreq-X
FrequencyBodyAccelerometerJerk-meanFreq-Y
FrequencyBodyAccelerometerJerk-meanFreq-Z
FrequencyBodyGyroscopeMean-X
FrequencyBodyGyroscopeMean-Y
FrequencyBodyGyroscopeMean-Z
FrequencyBodyGyroscopeStdDev-X
FrequencyBodyGyroscopeStdDev-Y
FrequencyBodyGyroscopeStdDev-Z
FrequencyBodyGyroscope-meanFreq-X
FrequencyBodyGyroscope-meanFreq-Y
FrequencyBodyGyroscope-meanFreq-Z
FrequencyBodyAccelerometerMagMean
FrequencyBodyAccelerometerMagStdDev
FrequencyBodyAccelerometerMag-meanFreq
FrequencyBodyAccelerometerJerkMagMean
FrequencyBodyAccelerometerJerkMagStdDev
FrequencyBodyAccelerometerJerkMag-meanFreq
FrequencyBodyGyroscopeMagMean
FrequencyBodyGyroscopeMagStdDev
FrequencyBodyGyroscopeMag-meanFreq
FrequencyBodyGyroscopeJerkMagMean
FrequencyBodyGyroscopeJerkMagStdDev
FrequencyBodyGyroscopeJerkMag-meanFreq
angletBodyAccelerometerMean-gravity
angletBodyAccelerometerJerkMean-gravityMean
angletBodyGyroscopeMean-gravityMean
angletBodyGyroscopeJerkMean-gravityMean
angleX-gravityMean
</pre>