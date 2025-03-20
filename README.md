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
