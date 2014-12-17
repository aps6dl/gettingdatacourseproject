my_xtrain=read.table("./train/X_train.txt",stringsAsFactors=FALSE)
my_xtest=read.table("./test/X_test.txt",stringsAsFactors=FALSE)

### 1. Merges the training and test data
my_merge_data=merge(my_xtrain,my_xtest,all=TRUE)


### 2. calculate mean and standard deviation
mymean=apply(my_merge_data,2,mean)
mysd=apply(my_merge_data,2,sd)

### 3. Descriptive Activity Names to name activities in data set
my_features=read.table("features.txt",stringsAsFactors=FALSE)

### 4. Labels the data set 
my_m=cbind(my_features,mymean,mysd)

### 5. write to txt file my_tidy_data 
my_tidy_data=write.table(my_m,file = "my_tidy_data.txt",row.names=FALSE)
