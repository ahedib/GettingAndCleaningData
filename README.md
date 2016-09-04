CourseraTidyDataProject
=======================

Repo for Coursera Data Science / R Data Cleaning Project

This serves as both the README and the code book for the data.

This analysis makes use of the "reshape2" package. Please install it before performing the analysis.

NOTE: Since the data has been processed already to calculate the various absolute displacements, it was determined that since the processed measurements were included, the individual X, Y, Z acelerometer were excluded.

This file uses the UCI HAR dataset available from http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones (University of California Irvine Human Activity Recognition) which are tracking accelerometer data collected from smartphones while test subjects performed various activities.

The data is provided in separate files and in two folders. There is both a 'test' and 'train' folder with data used to train an algorithm and one to test the predictions made. This analysis will combine the two sets as we are not performing any computer-directed learning on them.

In the data set, there is a file activity_labels.txt which translates the numeric activity designations into the 6 activities performed. The numeric activities are stored in the y_*.txt files and range from integers 1 to 6, inclusive.

The subject_*.txt files in the test and train directories associate the number of the subject being recorded, so there are multiple data readings for combinations of subject and activity.

The X_*.txt files contain the actual sensor readings and are described by the features_info.txt in the main directory of the data set.

Repository created to submit the classwork for Getting and Cleaning Data Class The R script run_analysis.R does the following with the raw data provided for the project. Step 1: Merges the training and the test sets to create one data set. Step 2: Extracts only the measurements on the mean and standard deviation for each measurement. Step 3: Uses descriptive activity names to name the activities in the data set Step 4: Labels the data set with descriptive variable names. Step 5: From the data set in step 4, creates a second, # independent tidy data set with the average of each variable for each activity and each subject.

For Step 1, The following was done with the raw data in the script.

The environment was set to use dplyr package and working directory where the datafiles are stored.
The activity labels, training and test datafiles, subjects and feature data where read into R dataframes for processing.
The training and test data were merged into the preliminary dataset using rbind.
The column names in the preliminary dataset where set to feature names from the feature dataframe.
For Step 2, The following was done.

Mean and std features were selected from features data frame
Second working dataframe was created with only the Mean and std features.
For Step 3, The following was done.

The third working dataframe was created and subjects and activities were added using cbind function
The column names were labeled with descriptive names
The activity id in the working dataframe was replaced with descriptive activity names.
Note, the activity names were not hardoded but derived from the activity lables using dplyr packages filter function.
For Step 4 and 5, the following was done

The working dataframe c_dataset1 was prepared to calculate average of each variable for each activity and each subject.
The aggregate function was used to calculate the average of each variable for each activity and each subject.
The final tidydata dataframe was created with appropriate column names.
The data was written to a file using the write.table function.

The analysis combined these files and, per the directions, selected out only the mean and standard deviation for each measurement.


