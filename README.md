# cytotoxicity_project_report

This report is based on a 10,000 records based cytotoxic dataset where I had to perform various operations to find meaningful insights from the data.

# 1.Data preprocessing

In this stage I first removed unnecessary columns from the dataset from which I will not be able to get valuable information like ids,names, dates etc.
Then in the modified dataset I checked all the null and duplicate values by performing 
          # df.isnull().sum()
          # df.duplicated().sum()


Here I saw that the cytotoxin_median raw and global_mad had null values around 6500
Then I wanted to identify those data that had hit more than 0 test samples.
So I created a filter through 
         #df[df["nhit"]>0]
After this step I got a modified dataset with 4284 rows and no null or duplicated values.
Now I checked the number of unique chemicals in the dataset and found out that in all cases of nhit>0 all the chemicals were unique.
For this I used the operation 
       #df[df["nhit"]>0]["chnm"].nunique()
The output came as 4284 which matches the original number of rows in the dataset.
So now I move to the trend analysis part.
