# Classifying_diseases_Gut_microbiota_ML

# General description
In this project, our aim was to classify diseases based on gut microbiota data using four different machine-learning algorithms. We looked into three different problems classifying five disease conditions, healthy and nonhealthy cases, and ulcerative colitis vs Crohn's disease classification. We have two general data sets, provided in the data.zip file, which contains the "baseline_data" and "fiber_data" files. The former contains the OTU values for different microbial communities at the genus level in the absence of any treatments, whereas the latter contains the baseline data in addition to the data of subjects in the presence of fiber treatment. In addition to comparing how the predictions of different machine learning algorithms vary using 5-fold cross-validation technique, we also investigated how the accuracies of different algorithms vary as a function of size. Accordingly, we have provided three notebook files. The "GitHub_classification.ipynb" for training and reporting classification metrics for different methods, "GitHub_size_effect.ipynb" for investigating the effects of the data size, and the "GitHub_compare_all_plots" for plotting the values. Additionally, we have provided the files prediction_data.zip (predictions matrices) and size_variation_data.zip used for plottings. For more infomration, refer to our publication available at: 


# Motivation
Human microbiome data has a potential to be a great source of information for the diagnosis and disease characteristics (phenotypes, disease course, therapeutic response) of diseases with dysbiotic microbiota community. However, multiple attempts to leverage gut microbiota taxonomic data for diagnostic and disease characterization have failed due to significant inter-individual variability of microbiota community and overlap of disrupted microbiota communities among multiple diseases. One potential approach is to look at the microbiota community pattern and response to microbiota modifiers like dietary fiber in different disease states. This approach is now feasible by availability of Machine learning that is able to identify hidden patterns in the human microbiome and predict diseases. 


Although there is a myriad of studies that have utilized ML for gut microbiota disease predictions, most of these studies have focused on distinguishing healthy from non-healthy subjects or predicting diseases that fall within similar categories of diseases, such as predicting GI disease, including IBD and esophagus diseases. As a result, it is vital to see if the predictive capability of the algorithms is limited to certain classes of diseases or if this capability can be extended to simultaneously, for example, predict multiple GI and systemic diseases where dysbiosis with overlapping microbiota community characteristics is present and what conclusions can be made of that as previous studies have reported an overlapping dysbiotic microbiota, for example, for Parkinson’s disease and IBD [14]. Additionally, whether it is possible to distinguish between the diseases after the subjects are given treatments, particularly fiber treatments, has not been investigated. As a result, in the current study, we aim to apply machine learning techniques to make predictions using the data that correspond to five different conditions, including Parkinson's disease (PD), Crohn's disease (CD), ulcerative colitis (UC), human immune deficiency virus (HIV), and healthy control (HC) subjects in the absence and presence of fiber treatments.

# Method

For all the classification problems in this study, we used four different ML algorithms, including the random forest (RF), support vector machine (SVM), artificial neural networks (ANN), and convolutional neural network (CNN). These methods have been successfully implemented to solve many problems that involve genomic datasets. To implement SVM and RF, we used scikit-learn classifiers [17] in python, where the one-vs-one scheme is used for multi-label classification. To implement ANN and CNN, the Multi-Layer Perceptron (MLP) classifier of scikit-learn and PyTorch were used, respectively. The architecture of CNN and ANN used in this study are shown in the below figure. The cross-entropy loss function was used with both CNN and ANN, where the output is the probability for each one of the classes. 

![Figure1-page-001](https://user-images.githubusercontent.com/60017299/202929796-f967a956-c496-4da9-82b2-fb264592494d.jpg)


# Results and conclusion:

The results suggest that SVM provides the highest values for all the classification metrics. However, the difference between the algorithms is not significant. The heatmap for the classification of the five conditions for one of the folds in the 5-fold cross-validation is shown in the below figure, for example, for the baseline data. 

![Figure3](https://user-images.githubusercontent.com/60017299/202929927-474515da-90e0-42d8-9442-87a7fa4b8739.jpg)

We have shown that it is possible to distinguish between the five conditions with accuracies as high as 95%, with SVM demonstrating the best performance among all methods. We have demonstrated that classifiers behave almost as perfect classifiers when it comes to classifying the HC and NH for both the baseline and fiber datasets. Additionally, we have shown that UC can be distinguished from CD with high accuracy using the OTU-based genomic data, even in the presence of the fiber treatment. The ability of our method to distinguish UC from CD with high accuracy has major clinical impact because current methods including invasive diagnostic tools like endoscopic procedures can fail to distinguish up to 20% of CD from UC. Accurate diagnosis of CD vs UC is essential for appropriate selection of surgical approach for treatment of these patients when they require surgery.






