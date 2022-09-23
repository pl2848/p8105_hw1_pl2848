# p8105_hw1_pl2848

# Install a package containing the penguins dataset
install.packages("palmerpenguins")


# Problem 1
# load the penguins dataset
data("penguins", package = "palmerpenguins")

# Calculate the mean of flipper length
mean(penguins$flipper_length_mm, na.rm = TRUE)
nrow(penguins)
ncol(penguins)
#About this data set:
# 1. Variables include species, island, bill_length_mm, bill_depth_mm, flipper_length_mm, body_mass_g, sex and year. 
# 2. There are 8 variables and 344 observations in this dataset.
# 3. mean (flipper leangth) = 200.9152

# create a scatter plot of bill length and flipper_length by species using ggplot
library(ggplot2)
p1_plot = ggplot(penguins, 
                aes(x = bill_length_mm, 
                y = flipper_length_mm, 
                color = species)) + geom_point()

#save the plot in the directory
ggsave("p1.pdf")

# Problem 2
library(tidyverse)
my_df = tibble(
  x = rnorm(10),
  y = x>0,
  z = "mailmansch",
  h = c("red","blue","yellow","red","blue","blue","yellow","blue","red","blue")
)

length(my_df$z)

mean(my_df$x)
mean(my_df$y)
mean(my_df$z)
mean(my_df$h)

mean(pull(my_df,x))