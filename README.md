# Binary_SVM_MTL

The code applies three linear svm based binary classification methods, i.e. global, local and multi-task learning, on a data set that has been decomposed into multiple tasks. 
- The global method learns a global model for the whole data
- The local method learns a model for each task seperately
- The MTL method assumes a multi-task relationship between the models and learns seperate models for each task with a regularizer that promotes the relationship among the tasks (see our paper for more details: https://arxiv.org/pdf/1705.10467.pdf)
The general idea of multi-task learning is to utilize the relationship between the tasks in order to boost the effective sample size. Therefore, MTL is usually expected to have a better performance than global and local when:
- The tasks are different enough such that having seperate models helps
- The tasks are related so that MTL can exploit such relationship
- The number of data points for each task is not very large and the localy learned model does not generalize well.

The input to the code should be a set of csv files. assuming there are m tasks, the number of csv files is 2m. For each task there should be two corresponding csv files. They should be named features_ and labels_ followed by the task number. The tasks should be numbered from 1 to m. For each task t, the features file includes a N_txd matrix of features, where N_t is the number of data points in task t and d is the feature length. The labels file for task t includes an N_tx1 vector of -1 and +1 which is the corresponding labels for the N_t data points in task t.

