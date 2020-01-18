# Define-factors
str(my_data_age_A)

#Age
age<- as.factor(my_data_age_A$agegroup_subj)
age<- factor(age,c(1,2,3),labels = c("Young","Middle","Old"))
consistency<- as.factor(my_data_age_A$Consistency)
