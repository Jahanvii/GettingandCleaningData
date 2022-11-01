The run_analysis.R script performs the data preparation and then followed by the 5 steps required as described in the course project’s definition.

### 1. Download the dataset
<ul>Dataset downloaded and extracted under the folder called UCI HAR Dataset</ul>

### 2. Assign each data to variables
<ul>features <- features.txt : 561 rows, 2 columns<br>
The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ.</ul>
<ul>activities <- activity_labels.txt : 6 rows, 2 columns<br>
List of activities performed when the corresponding measurements were taken and its codes (labels)</ul>
<ul>subject_test <- test/subject_test.txt : 2947 rows, 1 column<br>
contains test data of 9/30 volunteer test subjects being observed</ul>
<ul>x_test <- test/X_test.txt : 2947 rows, 561 columns<br>
contains recorded features test data</ul>
<ul>y_test <- test/y_test.txt : 2947 rows, 1 columns<br>
contains test data of activities’code labels</ul>
<ul>subject_train <- test/subject_train.txt : 7352 rows, 1 column<br>
contains train data of 21/30 volunteer subjects being observed</ul>
<ul>x_train <- test/X_train.txt : 7352 rows, 561 columns<br>
contains recorded features train data</ul>
<ul>y_train <- test/y_train.txt : 7352 rows, 1 columns<br>
contains train data of activities’code labels</ul>

### 3. Merges the training and the test sets to create one data set
<ul>X (10299 rows, 561 columns) is created by merging x_train and x_test using rbind() function</ul>
<ul>Y (10299 rows, 1 column) is created by merging y_train and y_test using rbind() function</ul>
<ul>Subject (10299 rows, 1 column) is created by merging subject_train and subject_test using rbind() function</ul>
<ul>Merged_Data (10299 rows, 563 column) is created by merging Subject, Y and X using cbind() function</ul>

### 4. Extracts only the measurements on the mean and standard deviation for each measurement
<ul>TidyData (10299 rows, 88 columns) is created by subsetting Merged_Data, selecting only columns: subject, code and the measurements on the mean and standard deviation (std) for each measurement</ul>

### 5. Uses descriptive activity names to name the activities in the data set
<ul>Entire numbers in code column of the TidyData replaced with corresponding activity taken from second column of the activities variable</ul>

### 6. Appropriately labels the data set with descriptive variable names
<ul>code column in TidyData renamed into activities</ul>
<ul>All Acc in column’s name replaced by Accelerometer</ul>
<ul>All Gyro in column’s name replaced by Gyroscope</ul>
<ul>All BodyBody in column’s name replaced by Body</ul>
<ul>All Mag in column’s name replaced by Magnitude</ul>
<ul>All start with character f in column’s name replaced by Frequency</ul>
<ul>All start with character t in column’s name replaced by Time</ul>

### 7. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject
<ul>FinalData (180 rows, 88 columns) is created by sumarizing TidyData taking the means of each variable for each activity and each subject, after groupped by subject and activity.</ul>
<ul>Export FinalData into FinalData.txt file</ul>
