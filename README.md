# Assign8

#Step 1 importing data

library(readxl)

Assignment_6_Dataset <- read_excel("D:/USF Spring 2024/R/Assignment-6-Dataset.xlsx")

Assignment_6_Dataset

#Run the commend "mean" using Sex as the category (use plyr package for this operation)

library(plyr)

Students_Average <- ddply(Assignment_6_Dataset, "Sex", transform.data.frame, Grade.Average=mean(Grade))

Students_Average

write.table(Students_Average, "Average of Students")

write.table(Students_Average, "Avg", sep = ",")

#Step2 Convert the data set to a dataframe for names whos' name contains the letter i, then create a new data set with those names, Write those names to a file separated by comma’s (CSV)


Students_i <- subset(Assignment_6_Dataset, grepl("i", Name))

Students_i

#step3 Write the filtered data set and convert it to CSV file

write.table(Students_i, "S_I", sep = ",")

