# Basics-of-R
This repository about basic concepts in R

Section 1 Comments

Exercise 1: Make a comment in R.
Exercise 2: Enter a comment into R without a # and note the error generated.
Solution 1 and 2
work this is a testing # Error: unexpected symbol in "work this"

Section 2 R Help
######################################################### #R HELP #########################################################
Exercise 3: Access the R help.
Exercise 4: Access the plot help.
Exercise 5: Generate two vectors, one being the numbers 1,2,3,...10 and the other being 2,4,6,...20. Exercise 6: Using the R help plot these.
Exercise 7: Using the R help add a main title, subtitle and label the axes.

#exercise 3
help.start()
?class

#exercise 4
?plot

#exercise 5
vec1 = c(1:10)   
vec2= seq(from=2,to=20,by=2) 

#exercise 6 and 7
plot(vec1,vec2, main = "main title", sub = "sub-tittle", xlab = "x axis title", ylab = "y axis title")


Section 3 Basic Calculations
################################################################################################################## 
Exercise 8: Run the following code
a=2
a=3
b<-3
a*b # note here the value of a*b is printed and then lost c=a*b # now the value of a*b is stored as c
b/a
3*6+234
exp(log(10))
a = 2; is.logical(a); is.list(a); is.numeric(a)
# Note that semicolons (;) let you run several calculations in the same line. # You could write the above as 4 separate lines if you prefer

Exercise 9: Save the code from Exercise 8 in a script file. Add appropriate comments to the code. Run the code again to ensure you have not generated any errors

#exercise 8 and 9
a = 2
a = 3
b <- 3
c = a*b
c
b/a
3*6+234
exp(log(10))
a = 2; is.logical(a); is.list(a); is.numeric(a)


Exercise 10: A manufacturing site are running a process; one of the unit operations in this process is a filtration step. There was 1000L of material entering the filter with a concentration of 2mg/L. 997L are recovered with a concentration of 1.95mg/L. Determine the yield.

#exercise 10
yield = ((997*1.95) / (1000*2))*100
yield

Section 4 Sourcing Data
######################################################### #LOAD AN AVAILABLE DATASET ######################################################### 
Exercise 11: Run the following code:
data(mtcars)
mtcars

#exercise 11
data(mtcars)
mtcars
View(mtcars)

Exercise 12: Use the plot function to plot mpg against quarter mile sprint time.

#plot mpg against quarter mile sprint time. means qsec on x-axis and mpg on y-axis
plot(mtcars$qsec, mtcars$mpg , main = "mtcars_data", col = "purple") 

Section 5 Data Types
######################################################## #VECTORS ######################################################## 
Exercise 13: Run the following code which generates a vector and then selects different entries in that vector, also finally measuring the length of that vector.
x = c(0.1, 2, 4.3, 3.1, 5)
x[2] # returns the second value in that vector
x[1:3] # returns the first three values
x[-(1:3)] # gives all but the first three elements
x[x>3] # selects the subset of values in x greater than 3 N = length(x) # stores the length of x

solution
#vectors - exercise 13
x = c(0.1, 2, 4.3, 3.1, 5)
# returns the second value in that vector
x[2] 
# returns the first three values
x[1:3]
# gives all but the first three elements remove because of negative sign
x[-(1:3)]
# selects the subset of values in x greater than 3
x[x>3] 
# stores the length of x
N = length(x)
N


Exercise 14: Generate a new vector y where y=2x+1.
solution
x = c(0.1, 2, 4.3, 3.1, 5)
y = 2*x + 1
y

Exercise 15: Calculate the mean, median and standard deviation of both x and y.
solution
mean(x)
median(x)
sd(x)  #standard deviation
mean(y)
median(y)
sd(y)

Exercise 16: Use the seq() function to generate a vector containing the following values: -5, -4, -3, ..., 3, 4, 5
solution
seq (from = -5 , to = 5)

Exercise 17: Use the rep function to repeat the vector x twice.
solution
rep(x , times = 2)

Exercise 18: Run the following code. Note the relationship between the different fruits and their values. #Vectors may also contain characters or strings:
fruit <- c(5, 10, 4)
names(fruit) <- c("orange", "banana", "apple")
lunch <- fruit[c("apple","orange")]

solution
fruit <- c(5, 10, 4)
fruit
names(fruit) <- c("orange", "banana", "apple")
names(fruit)
lunch <- fruit[c("apple","orange")]
lunch


Section 6 Matrices
########################################################
#MATRICES
########################################################
# Create a vector
x = c(1, 2, 3, 4, 5, 6, 7, 8, 9)
# Now make it a 3×3 matrix:
matrix(x, ncol = 3) # note how this is arranged. #If we prefer arranging by rows:
M = matrix(x, ncol = 3, byrow = TRUE)
#The matrix now has dimensions:
dim(M)
ncol(M)
nrow(M)


#What do the following do? t(M); aperm(M, c(2,1)) diag(M)
det(M)
#define two matrices A and B as below: A <- M; B <- t(M)
#Element-by-element product:
A * B #(if A and B are square)
#Matrix product:
A %*% B
# note how these are considerably different!


########################################################
#ARRAYS
########################################################
h = seq(1, 24, by=1)
Z <- array(h, dim=c(3,4,2)) Z[1,1,1]; Z[1,2,2]


########################################################
#LISTS
########################################################
Lst <- list(name="Fred", wife="Mary", no.children=3, child.ages=c(4,7,9)) Lst[[2]]
Lst[[4]][1]
#It is important to be familiar and comfortable with indexing in this way #notice the difference in the following two outputs
Lst[4]
Lst[[4]]
#You can also index into a list (or dataframe) using $.
# If you type Lst$, you should get a prompt from RStudio of the available sublists/variables/ Lst$child.ages



########################################################
#Data frames
########################################################
Exercise 19: Investigate the as.Date() function and the “Date” variable type using the help function.
Exercise 20: Create a data frame called emp.data with the following information (input the state_date variable as a “Date” variable [not a string or numeric]).
emp_id
emp_name      salary
start_date
2012-01-01
2013-09-23
2014-11-15
2014-05-11
2015-03-27
1 Rick 623.30
2 Dan 515.20
3 Michelle      611.00
4 Ryan 729.00
5 Gary 843.25



#Matrices......
#Creating a vector
x = c(1, 2, 3, 4, 5, 6, 7, 8, 9)

#making it a 3 by 3 matrix
matrix(x, ncol = 3)

#If we prefer arranging by rows:
M = matrix(x, ncol = 3, byrow = TRUE)
M

#dimensions and no. of rows and columns in a matrix it defines
dim(M)
ncol(M)
nrow(M)
t(M)  # transpose of matrix
aperm(M, c(2,1)) # transpose of matrix , line 103 and this both are identical
t(M); aperm(M, c(2,1))
diag(M)
#this is determinant of a matrix
det(M)


#defining two matrices
A <- M ; B <- t(M)
A
B

#Element-by-element product:
A * B #(if A and B are square)

#Matrix product:
A %*% B


#ARRAYS
h = seq(1, 24, by=1)
h
Z <- array(h, dim=c(3,4,2))
Z
Z[1,1,1]; Z[1,2,2]


#LISTS

Lst <- list(name="Fred", wife="Mary", no.children=3, child.ages=c(4,7,9))
Lst
Lst[[2]]
#extract 4th index first then in that 1 st index
Lst[[4]][1]
#4th index in list with the header name
Lst[4]
#here it will also give the same thing without the header name
Lst[[2]]
Lst[[4]]
#$ is used to filter out the particular thing
Lst$child.ages


#Data Frames
#exercise 19
?as.Date()
?date   # it will tell current date and time

#exercise 20
emp.data<- read.csv(file.choose())
emp.data


#another method
emp_id <- 1:5
emp_name <- c("Rick", "Den", "Michelle", "Ryan","Gary") ...the result of this wll come in factor to convert into chararcter
salary <- c(632.3, 515.2, 611.729, 843.25)
start_date <- as.Date(c("2012-01-01", "2013-09-23", "2014-11-15","2014-05-11",))

emp.date <- data.frame(emp_id,emp_name,salary,start_date)

str(emp.data)



Exercise 21: Run the following code and note the output
# Get the structure of the data frame.
str(emp.data)
#note the different types of variables
# Print the summary.
summary(emp.data)

solution
str(emp.data)
summary(emp.data)



Exercise 22: Add a new column to the emp.data called “dept”, to give the below result
emp_id   emp_name    salary    start_date      dept
1 Rick
2 Dan
3 Michelle
4 Ryan
5 Gary
623.30    2012-01-01      IT
515.20    2013-09-23      Sales
611.00    2014-11-15      IT
729.00    2014-05-11      HR
843.25    2015-03-27      Finance

solution
emp.data <- cbind(emp.data, dept=c("IT","Sales", "IT","HR","Finance"))
emp.data

Exercise 23: Create a separate dataframe called emp.newdata with the below information:
emp.newdata<- data.frame("emp_id" = 6:8, "emp_name" = c("rasmi","pranab","tusar"), "salary" = c(578.0 , 722.5 ,632.8) ,"start_date" = c('21/05/2013' , '30/07/2013', '17/06/2014'),"dept" = c("IT","Operations","Finance"))
emp.newdata

Exercise 24: Combine the two dataframes, emp.data and emp.newdata, into a separate data frame called emp.finaldata.
emp.finaldata <- rbind(emp.data , emp.newdata)
emp.finaldata

Exercise 25: Add a new employee to emp.finaldata, named “John” who works in “HR”. He began on 2013-07-21 and his salary is 533.30.
emp_id emp_name  salary  start_date       dept
6 Rasmi
7 Pranab
8 Tusar
578.0   2013-05-21       IT
722.5   2013-07-30       Operations
632.8   2014-06-17       Fianance

solution
nRow <- data.frame ("emp_id"= 6 , "emp_name" = "john", "salary" = 533.30 , "start_date" = '21/07/2013', "dept" ="HR")
rbind(emp.finaldata , nRow)

