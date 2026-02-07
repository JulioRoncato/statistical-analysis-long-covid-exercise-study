# Data Cleaning Script (Representative)
data <- read.csv("data/simulated_dataset.csv")
data$Group <- factor(data$Group)
data$Sex <- factor(data$Sex)
summary(data)

library(tidyverse)
data <- read.csv("data/simulated_dataset.csv")

data %>%
  group_by(Group, Sex) %>%
  summarise(
    mean_HR = mean(Heart_Rate_Peak),
    sd_HR = sd(Heart_Rate_Peak)
  )

library(ggplot2)
data <- read.csv("data/simulated_dataset.csv")
ggplot(data, aes(x = Group, y = VO2max, fill = Sex)) +
  geom_boxplot() +
  theme_minimal()
