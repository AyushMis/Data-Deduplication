
The problem of data duplication is very common in every database which means database have repeated data of same person with unnecessary changes. After learning so much, we human may recognize and further chatagorize them as “Silly Mistakes” on the basis of our continuous learning. But as we see in todays world that everything needs to be automated so that it can reduce human’s manual work. Therefore data de-duplication is one the main area of concern where researchers are putting their efforts to solve this problem in a way more effective and efficient manner.

VISUALIZATION
For our initial work, I visualised the data and anaylsed it as deeply as possible and then started my work on it because analysis of dataset itself plays a major role. I have gone through various research articles related to this same work and have read many algorithms and models which they have proposed for the learning.

Work done till now by many researchers is based on active learning in which learning takes place by the machine learning model as the user manually assigns the results whether the two rows(i.e. two data entries) are duplicate of each other or not. In this approach, initially the model gives very bad results while training but as soon as it learns from the manual labelling whether two entries are same or different, it’s accuracy increases and is able to give very accurate results. 
Drawback: The only drawback of this approach is that it requires manual labelling at first and that manual labelling is not known whether for how many entries, the data should be manually labelled first.

PREPROCESSING
Therefore for simplification of work and without the need of manual labelling, I divided the whole dataset into various clusters on the basis of some constraint i.e. if:
1) If date of birth is same and
2) gender of person is identical

then the entry1 and entry2 should be clustered together. 

NOTE: There are many other possible ways to cluster our data like we can include person with identical surname with the above mentioned parameters to cluster the data into the same cluster.
		
	entry1(lastname)==entry2(lastname) or entry1(firstname)==entry2(firstname)

After clustering the whole dataset, what I have assumed that the entries which are clustered together are duplicate of each other. This assumption is done so that no manual labelling should be needed. 

Next what we have done is, we used a jellyfish library of python to find the distance between two data entries(each entry is a combination of characters and integers). So for each pair in the dataset, distance is calculated between various attribute(name, age, gender). After finding the distance, we have labelled each distance with 1 if in same cluster and 0 otherwise. 

LEARNING AND OUTPUT
After building the dataset to finally train our model, we then trained it using KNN classifier model and finally getting an accuracy ranging from 98.5% to 98.9% with different values of k ranging from 1 to 25.
I have also trained the same dataset using different model such as Logistic Regression which is giving accuracy of 96.23%. 
So using my approach, if compared, KNN classifier is giving more accuracy than other algorithms.

In the above mentioned approach, there are many drawbacks which should be corrected but this approach doesn’t involve manual labelling of the dataset.

