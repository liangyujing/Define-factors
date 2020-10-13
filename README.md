# Define-factors
str(my_data_age_A)

#Age
age<- as.factor(my_data_age_A$agegroup_subj)
age<- factor(age,c(1,2,3),labels = c("Young","Middle","Old"))
consistency<- as.factor(my_data_age_A$Consistency)

# define factors
data$trial_counter <- as.integer(factor(data$trial_counter,levels=unique(data$trial_counter))) 
data$subject <- as.character(as.factor(data$subject))

# create factor of solution-type and convert RT and confidence to numeric values with a certain amount of decimal places left
experimental_df$solution_type<-as.factor(experimental_df$solution_type)
experimental_df$RT<-as.numeric(experimental_df$RT, digits = 3)
experimental_df$confidence<-as.numeric(experimental_df$confidence, digits = 2)
summary(experimental_df)
