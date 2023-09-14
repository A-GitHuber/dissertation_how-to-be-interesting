## dissertation_how-to-be-interesting
The code and dataset for dissertation


# First of all, the **data** folder mainly contains data preprocessing.

In the txt.ipynb file, we extract the original json file into a txt file.

In the overall.ipynb file, we preprocess and clean the original json file, extract it into a csv file, and then divide the csv file into conversations and save them as txt files.


# Then, use GisPy.zip to get the gis score of each group of conversations, and store the results in the results folder.

In the question.ipynb file, we count the number of questions in each conversation.

In the NIDF.ipynb file, we count the number of rare words in each conversation under different thresholds.

In the correlation.ipynb file, we mainly explore the relationship between the three input variables and the four target variables. The input variables include gis score, the number of questions in each conversation and the number of rare words in each conversation. The target variables are expected interest (EXP INT), interest (INT), the difference between EXP INT and INT, and there are some target variables that are slightly more complicated. The first one is sign(2-class), if the difference between EXP INT and INT is greater than or equal to 0, it will be treated as 1. If the difference between the two is less than 0, it will be treated as 0. And the second one is sign(3-class）, which is mainly the same as sign(2-class), except that when the difference between INT and EXP INT is negative, it is regarded as -1, and when the difference between the two is 0, it is regarded as 0. This means , there are -1, 0 and 1 in sign3.

After explaining the variable information, we conducted a correlation coefficient analysis on the input variables and target variables, and drew a correlation heat map.

After that, we also used gis score, the number of questions and the number of rare words under different thresholds to build neural network classifiers for different target variables, hoping to get the best model and discover the relationship between dialogue and interest. relation. Here we will explain the differences between the target variables of these classifiers. EXP INT, INT and difference mainly regard the corresponding data in the original data as the target variable, so the classifier trained in this way is a 5-class classifier. difference2 first uses EXP INT and INT in the original data to train two 5-class classifiers, and then calculates the difference between the results and compares it with the difference in the original data to obtain its performance. As mentioned above, sign2 and sign3 treat the difference between EXP INT and INT as Category 2 and Category 3 respectively.

Finally, in the plot.ipynb file, we summarize the performance of these six classifiers to make a performance graph. Finally, in the plot.ipynb file, we summarize the performance of these six classifiers to make a performance graph, and store the lossless vector graph in the image folder.
