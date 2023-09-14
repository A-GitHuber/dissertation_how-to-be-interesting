## dissertation_how-to-be-interesting
The code and dataset for dissertation


# First of all, the **data** folder mainly contains data preprocessing.

In the txt.ipynb file, we extract the original json file into a txt file.

In the overall.ipynb file, we preprocess and clean the original json file, extract it into a csv file, and then divide the csv file into conversations and save them as txt files.


# Then, use GisPy.zip to get the gis score of each group of conversations, and store the results in the results folder.

In the question.ipynb file, we count the number of questions in each conversation.

In the NIDF.ipynb file, we count the number of rare words in each conversation under different thresholds.

In the correlation.ipynb file, we mainly explore the relationship between the three input variables and the four target variables. The input variables include gis score, the number of questions in each conversation and the number of rare words in each conversation. The target variables are expected interest (EXP INT), interest (INT), the difference between EXP INT and INT, and there are some target variables that are slightly more complicated. The first one is sign(2-class), if the difference between EXP INT and INT is greater than or equal to 0, it will be treated as 1. If the difference between the two is less than 0, it will be treated as 0. And the second one is sign(3-class）, which is mainly the same as sign(2-class), except that when the difference between INT and EXP INT is negative, it is regarded as -1, and when the difference between the two is 0, it is regarded as 0. This means , there are -1, 0 and 1 in sign3.
