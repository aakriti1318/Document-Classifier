# Document Classifier
The idea behind using a document classifier for a job portal is to give a seamless experience to job seekers as well as to recruiters. 
Document Classifier helps to classify the document even if the name of the .pdf or .jpg file name is not matching with the actual document enclosed in it. 

2.1 Dataset: For this POC, I have collected datasets from several websites. Dataset mainly consists of personal documents data includes Aadhar Card, Pan Card, Marksheets...
Some Examples of Inferring topics with keywords
Aadhar Card -- Government, India, Name, DOB, Gender, Aadhar
PAN card -- Income, Tax, Department, India, Permanent, Account, Number, Card, Name, Father, Date, Birth, Signature.

![image](https://user-images.githubusercontent.com/56245613/169650458-faee69bf-eff0-408f-b017-c9b21141c110.png)

Implementation: 
Identifying file as image or pdf. 
If pdf then converting it into IMG (Using Pillow (PyMuPDF Library) extract all image in .png format)
Otherwise, continue. 
Text Extraction - tesseract (OCR) / Apache Tika  to extract text from images. 
Identifying words - Supervised machine learning where all data points, the data extracted from each document, in the training data is labelled with the right answer, the correct category for that document. 
The job of the machine learning algorithm will then be to find similarities between the documents in each category.
Multinomial Naive Bayes classifier - 
works by first going through all the training data and counting the occurrence of each word in each category.
Using that data it can calculate the probability of each word belonging to every category. 
When a new document needs to be categorized it calculates the probability of that document belonging to each category by combining the probability of each word in it and then choosing the category with the highest probability.
Testing - Precision and Recall
