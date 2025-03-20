# Create a 3-dimensional array
arr <- array(c(1:12), dim = c(3, 2, 2))
print("Array:")
print(arr)

# Create a list with different types of elements
my_list <- list(Name = "Alice", Age = 25, Scores = c(90, 85, 88))
print("List:")
print(my_list)


# Create a data frame
students <- data.frame(
  Name = c("Alice", "Bob", "Carol"),
  Age = c(25, 22, 24),
  Score = c(90, 85, 88)
)
print("Data Frame:")
print(students)



Create an array containing the scores of students across three subjects. Use a list to store additional information about the students (e.g., names and ages). Finally, combine this data into a data frame to display the students' names, ages, and average scores for each subject.

# Step 1: Create an array for student scores (3 students, 3 subjects)
scores_array <- array(c(85, 90, 88, 78, 80, 84, 92, 95, 89), dim = c(3, 3))
print("Scores Array:")
print(scores_array)

# Step 2: Create a list to store additional student information
student_info <- list(
  Names = c("Alice", "Bob", "Carol"),
  Ages = c(20, 21, 22)
)
print("Student Info List:")
print(student_info)

# Step 3: Combine data into a data frame with average scores
average_scores <- rowMeans(scores_array)  # Calculate row-wise averages
students_df <- data.frame(
  Name = student_info$Names,
  Age = student_info$Ages,
  Average_Score = average_scores
)
print("Students Data Frame:")
print(students_df)


 )Create a Matrix using R  and Perform the operations addition, inverse, transpose  and multiplication operations.
 # Create a 2x2 matrix A
A <- matrix(c(1, 2, 3, 4), nrow = 2, ncol = 2)
print("Matrix A:")
print(A)

# Create another 2x2 matrix B
B <- matrix(c(5, 6, 7, 8), nrow = 2, ncol = 2)
print("Matrix B:")
print(B)

# Matrix addition (A + B)
C <- A + B
print("Matrix A + Matrix B:")
print(C)

# Inverse of matrix A (if it is invertible)
A_inv <- solve(A)
print("Inverse of Matrix A:")
print(A_inv)

# Transpose of matrix A
A_transpose <- t(A)
print("Transpose of Matrix A:")
print(A_transpose)

# Matrix multiplication (A * B)
D <- A %*% B
print("Matrix A * Matrix B:")
print(D)

Using R Execute the statistical functions: mean, median, mode, quartiles, range, inter quartile range histogram
# Create a sample dataset
data <- c(1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 2, 3, 5, 7, 8, 6, 9, 10)

# 1. Mean
mean_value <- mean(data)
cat("Mean:", mean_value, "\n")
# 2. Median
median_value <- median(data)
cat("Median:", median_value, "\n")

# 3. Mode (custom function for mode)
# Mode is the value that appears most frequently in the dataset.
getmode <- function(v) {
  uniqv <- unique(v)
  uniqv[which.max(tabulate(match(v, uniqv)))]
}

mode_value <- getmode(data)
cat("Mode:", mode_value, "\n")

# 4. Quartiles
quartiles <- quantile(data)
cat("Quartiles:", quartiles, "\n")

# 5. Range
range_value <- range(data)
cat("Range:", range_value, "\n")

# 6. Interquartile Range (IQR)
IQR_value <- IQR(data)
cat("Interquartile Range (IQR):", IQR_value, "\n")

# 7. Histogram
hist(data, main="Histogram of Data", xlab="Value", ylab="Frequency", col="skyblue", border="black")


Using R import the data from Excel  and perform the function mean, median, mode

# Install necessary packages if not already installed
install.packages("readxl", dependencies = TRUE)
install.packages("openxlsx", dependencies = TRUE)

# Load the required packages
library(readxl)
library(openxlsx)

# Specify the file path to your Excel file
file_path <- "C:/Users/PC-31/Downloads/FSI_2023.xlsx"  # Replace with your file path

# Using readxl to read the Excel file
# Read the entire file (first sheet by default)
data_readxl <- read_excel("C:/Users/PC-31/Downloads/FSI_2023.xlsx")

# Print the first few rows of the data using readxl
cat("Data from readxl:\n")
print(head(data_readxl))

# Using openxlsx to read the Excel file
# Read the first sheet
data_openxlsx <- read.xlsx(file_path, sheet = 1)

# Print the first few rows of the data using openxlsx
cat("\nData from openxlsx:\n")
print(head(data_openxlsx))

# Function to calculate mode
get_mode <- function(x) {
  uniq_x <- unique(x)
  uniq_x[which.max(tabulate(match(x, uniq_x)))]
}

# Calculate mean, median, and mode for each numeric column
cat("\nCalculating Mean, Median, and Mode for each numeric column:\n")

# Loop through each numeric column
for (col in names(data_readxl)) {
  if (is.numeric(data_readxl[[col]])) {
    mean_value <- mean(data_readxl[[col]], na.rm = TRUE)
    median_value <- median(data_readxl[[col]], na.rm = TRUE)
    mode_value <- get_mode(data_readxl[[col]])
    
    cat("\nColumn:", col, "\n")
    cat("Mean:", mean_value, "\n")
    cat("Median:", median_value, "\n")
    cat("Mode:", mode_value, "\n")
  }
}

Perform the Linear Regression using R. 

# Example dataset
x <- c(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
y <- c(1.2, 2.5, 3.5, 4.6, 5.5, 6.7, 7.8, 9.0, 10.1, 11.2)

# Combine x and y into a data frame
data <- data.frame(x, y)

# Fit the linear model
model <- lm(y ~ x, data = data)

# Show the summary of the model
summary(model)

# Make predictions for new data
new_data <- data.frame(x = c(11, 12, 13))
predictions <- predict(model, newdata = new_data)
print(predictions)

# Plot the data and the regression line
plot(data$x, data$y, main = "Linear Regression", xlab = "X", ylab = "Y", pch = 19)
abline(model, col = "blue")



Part 2:

Compute the Linear Least Square Regression using R

# Step 1: Prepare your data
# Example data for x (independent variable) and y (dependent variable)
x <- c(1, 2, 3, 4, 5)
y <- c(2, 4, 5, 4, 5)

# Combine the data into a data frame
data <- data.frame(x = x, y = y)

# Step 2: Fit the linear model (Linear Least Squares Regression)
# The formula 'y ~ x' indicates a linear relationship between y and x
model <- lm(y ~ x, data = data)

# Step 3: Display the model summary
# This will show the coefficients, R-squared value, and p-values
print("Linear Regression Model Summary:")
print(summary(model))

# Step 4: Plot the data points and the fitted regression line
# Adjusting the margins to avoid the "figure margins too large" error
par(mar = c(4, 4, 2, 1))

# Create a scatter plot of the data points
plot(x, y, main = "Linear Regression", xlab = "X", ylab = "Y", pch = 16, col = "red")

# Add the fitted regression line
abline(model, col = "blue")

# Step 5: Predict new values (optional)
# For example, predicting the value of y when x = 6
new_x <- data.frame(x = 6)
predicted_y <- predict(model, new_x)

# Display the predicted value
cat("Predicted value of y when x = 6:", predicted_y, "\n")

Compute the Least squares means using R.

# Install and load the emmeans, ggplot package
install.packages("emmeans")  # Uncomment this line if the package is not installed
install.packages("ggplot") 
library(emmeans)
library(ggplot2)
# Example dataset
x <- c(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
y <- c(1.2, 2.5, 3.5, 4.6, 5.5, 6.7, 7.8, 9.0, 10.1, 11.2)

# Fit a linear regression model
model <- lm(y ~ x)

# Compute least squares means
lsmeans_result <- emmeans(model, ~ x)

# Display the result
print(lsmeans_result)

# Plot the Least Squares Means
plot(lsmeans_result)
