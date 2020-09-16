Code Book
================

INTRODUCTION
------------

This code book is used for

-   outlining the analyses to clean up the data
-   interpreting the variables in the tidyData.txt document

The present version is modified from the original code book provided by Coursera Data Science Specialization Peer-graded Assignment: Getting and Cleaning Data Course Project that can be downloaded from [here](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip)

ANALYSIS PIPELINE
-----------------

### 1. Read in the files and merge data

-   label files: activity\_labels.txt and features.txt
-   training data: subject\_test.txt, X\_test.txt (assign column names as feature names), and y\_test.txt
-   test data: subject\_train.txt, X\_train.txt (assign column names as feature names), and y\_train.txt
-   merge all training files horizontally into one training data
-   merge all test files horizontally into one test data
-   merge the training data and test data vertically into one data

### 2. Extract only the mean and standard deviation of the measurments

-   keep the subject Id and actvitiy columns
-   identify column names with 'mean' or 'std'

### 3. Use descriptive activity names to name the activities in the data set

-   change the activity column from numberse 1-6 to descriptive activities: WALKING, WALKING\_UPSTAIRS, WALKING\_DOWNSTAIRS, SITTING, STANDING, LAYING

### 4. Label the data set with descriptive variable names

-   remove the () in the columns to make the variable names cleaner and easier to read
-   for a description of the variables, please refer to 'FEATURE VARIABLES' below

### 5. Create a second, independent tidy data set with the average of each variable for each activity and each subject

utilize the dplyr package to

-   group the data set by subject ID and activity (group\_by)
-   summarize the grouped data set and calculate the average of each variable (summarise\_all(funs\_mean))

For the detailed script, please refer to the run\_analysis.R file.