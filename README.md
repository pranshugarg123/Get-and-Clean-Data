# Get-and-Clean-Data
Steps Involved
1. Download and Unzip the Dataset
The UCI HAR Dataset is first downloaded and unzipped into a local directory called ./getcleandata.

2. Reading Data Files
We read the training and testing datasets into R. The files include:

X_train.txt and X_test.txt: Containing the measurement data.
y_train.txt and y_test.txt: Containing activity labels for training and test sets.
subject_train.txt and subject_test.txt: Containing the subject identifiers for each activity.
3. Merging the Data
We combine the training and test datasets into a single data frame using cbind() for combining columns and rbind() for combining rows. The final dataset contains the activity and subject identifiers along with the measurement data.

4. Extracting Mean and Standard Deviation Measurements
We extract only the measurements related to the mean and standard deviation for each measurement. This is done using grepl() to identify the columns that contain "mean()" and "std()".

5. Descriptive Activity Names
The activity labels are merged into the dataset, replacing the activity IDs with descriptive activity names (e.g., WALKING, SITTING, etc.) for better understanding and readability.

6. Labeling the Data
The column names are cleaned and made more descriptive. The following changes are made:

Replace "t" with "time" and "f" with "frequency" to clarify the type of measurements.
Replace abbreviations like "Acc" with "Accelerometer", "Gyro" with "Gyroscope", and "Mag" with "Magnitude".
Correct redundant labels like "BodyBody" to "Body".
7. Creating a Tidy Data Set
A second tidy data set is created by calculating the average of each variable for each combination of subjectID and activityID using group_by() and summarise_all() from the dplyr package. This new dataset is then written to a text file (tidySet.txt).

Final Output
The final tidy dataset (tidySet.txt) contains the average of each measurement for every subject and activity, ready for further analysis or modeling.

