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

# create two data frames one with correct and incorrect responses and one with only correct responses
mixedef_correct<-experimental_df %>%
  filter(ACC == 1) %>% 
  filter(solution_type != 3) %>% 
  mutate(baseline_RMSSD = as.numeric(baseline_RMSSD),
         HF_HRV = as.numeric(HF_HRV),
         num_reject_IBI = as.numeric(num_reject_IBI))

mixedef_correct_incorrect<-experimental_df %>%
  filter(solution_type != 3) %>% 
  mutate(baseline_RMSSD = as.numeric(baseline_RMSSD),
         HF_HRV = as.numeric(HF_HRV),
         num_reject_IBI = as.numeric(num_reject_IBI))
summary(mixedef_correct_incorrect)

sd(mixedef_correct_incorrect$age)
