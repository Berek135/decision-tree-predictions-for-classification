Decision Tree Predictions for Classification 


Department of Computer Science, University of the People 
Univ 4407: Data Mining and Machine Learning 
James Mukyo 
February 24, 2025




    Part 1: Print decision tree 
  a. We begin by setting the working directory, loading the required packages (rpart and mlbench) and then loading the Ionosphere dataset.
  #
  setwd(“working directory”) 
  #
  library(rpart)
  #
  library(mlbench)
  #
  data(Ionosphere)

![image](https://github.com/user-attachments/assets/72a1aff2-09c7-4e92-9d49-c1542494eca0)

b. use the rpart() methods to create a regression tree for the data
  rpart(Class~.,Ionosphere)

c. Use the plot() and text() methods to plot the decision tree


![image](https://github.com/user-attachments/assets/dba05956-5293-4e4d-a8a6-ca8b58d76fe7)
  ![image](https://github.com/user-attachments/assets/62b465f1-e742-4a7a-9d7a-362e0c52076b)



Part 2: Estimate Accuracy
  
  a. split the data a test and train subsets using the sample() method
  >set.seed=(42)
  >train=sample(1:nrow(Ionosphere),200) b. Use the rpart method to create a decision tree using the training dat

![image](https://github.com/user-attachments/assets/fa5a1077-7083-42af-9db1-3d5a2cafbeba)

b. Use the rpart method to create a decision tree using the training data
  
  rpart(Class~.,Ionosphere,subset=train)

  ![image](https://github.com/user-attachments/assets/abc9631c-695f-4afa-8e3f-25a7232523a6)


c.use the predict method to find the predicted class labels for the testing data
>rpart.pred=predict(rpart.ionosphere, Ionosphere. test,type="class")

![image](https://github.com/user-attachments/assets/45ad44ed-6929-4b44-bc09-53dba80eb04e)



d.Use the table method to create a table of the predictions versus true 
labels and then compute the accuracy. The accuracy is the number of correctly 
assigned good cases (true positives) plus the number of correctly assigned 
bad cases (true negatives) divided by the total number of testing cases.

>table(rpart.pred,Ionosphere$Class[-train])
>
>>table(rpart.pred,Ionosphere$Class[-train])


![image](https://github.com/user-attachments/assets/97c962f8-8e6c-4005-ab1b-d92fd7646679)



References 

James, G., Witten, D., Hastie, T., & Tibshirani, R. (2013).  An introduction to statistical learning with applications in R. New York, NY: Springer.  Read Chapter 8.
Therneau, T., (2025), Recursive Partitioning and Regression Trees, package ‘rpart’ https://cran.r-project.org/web/packages/rpart/rpart.pdf 


==============================///////////////////////=========================
