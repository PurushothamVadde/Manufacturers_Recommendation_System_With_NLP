# Manufacturers Recommendation System With Natural Language Processing

![head](https://github.com/PurushothamVadde/Manufacturers_Recommendation_System_With_NLP/blob/master/images/manufacturer.jpeg)

## Tools and Packages:
* Programming :Python
* Webscraping :beautifulSoup
* Data Visualisation :Tableau
* Natural Language Processing : NLTK
* Other Packages : sklearn, cosine_similarity, pandas, re, np


## About Project:
As part of this project we are applying the Natural Language Processing on manufacturing capabilities of each manufacturer and the Input text (capabilities that user looking for) and provide the closest results related to the Input text to the user.\
To get the data of manufacturers, we followed the web scaring technique by which we collected the data from many online resources such as manufacturing websites, social media etc. After the collection of data we cleaned the data and used the TFIDF vectorizer to convert the input and manufacturer capabilities text into numerical matrix format, and we used the cosine similarity score to get the similarity score between the Input Text and Manufacturer capabilities and we displayed the manufacturers by highest similarity score to the user so that the user will get the suggestions based on the highest similarity score (suggestions that are related closely to the input text).
The detailed steps are mentioned as below.

- [Collecting the Manufacturers Data](#collecting-the-manufacturers-data)
- [UserInput](#userinput)
- [Getting the Data based on the Input State](#getting-the-data-based-on-the-input-state)
- [Text Normalization](#text-normalization)
- [Text Vectorization](#text-vectorization)
- [Calculating the Similarity Score using Cosine Similarity](#calculating-the-similarity-score-using-cosine-similarity)
- [Results](#results)
- [Conclusion](#conclusion)


### Collecting the Manufacturers Data:
We have collected the Manufacturing details through web scraping of multiple online websites and social media etc., The Manufacturer Details contains columns as described below:
> Name       		  	          : Manufacturers name             
> Address                 		: Manufacturers Address\
> Manufacturer_state     	    : State where the manufacturer is present\
> Number                  		: phone number of Manufacturer\
> URL                     		: Website Url of Manufacturer\
> Employees               		: No of Employees working at Manufacturer\
> Description            		  : About Manufacturer\
> Capabilities_Overall    	  : Capabilities of Manufacturer
#### CNC Manufactures data Statewise in USA
![CNC](https://github.com/PurushothamVadde/Manufacturers-Recommendation-System-With-Natural-Language-Processing/blob/master/images/CNC_Manufactures.png)
#### Welding Manufactures data Statewise in USA
![Welding](https://github.com/PurushothamVadde/Manufacturers-Recommendation-System-With-Natural-Language-Processing/blob/master/images/welding.png)
#### Casting Manufactures data Statewise in USA
![Casting](https://github.com/PurushothamVadde/Manufacturers-Recommendation-System-With-Natural-Language-Processing/blob/master/images/Casting.png)
#### About Capabilities of Manufacturer:
The  Capabilities column in the data table contains the complete list of operations or services  that each manufacturer providing, 
Below list is the example of capabilities of single manufacturer:

> ('Assembly Machinery', 'Automotive Parts', 'Bending Services', 'Boring Services', 'Broaching Services', 'Custom Machinery', 'COVID-19 Response', 'Cutting Services', 'Cylinders',  'Drilling Services', 'Electronic Components', 'Extrusion Services', 'Fabrication Services', 'Hydraulic Equipment', 'Hobbing Services', 'Job Shop Services', 'Knurling Services', 'Machining', 'Machinery', 'Maintenance and Repair Services', 'Medical Components', 'Milling Services', 'Motors', 'Power Units', 'Plastics', 'Pumps', 'Tapping Services', 'Testing  Services', 'Tier 2 Medical Mfg. Supplies, Materials, Components & Services', 'Turning Services', 'Valves', 'Welding Services', 'Winding Services')

###  UserInput :
As Input we will Accept  the state of Manufacturer and Manufacturing Capabilities that user is looking for.

> Example:\
> Input State = “CA” \
> Input Capabilities = ["COVID-19 Response"]

### Getting the Data based on the Input State:
Based on the state entered as input we will select the manufacturers capabilities from our data which are from the input state and perform the next steps on that data.

### Text Normalization:
In this step we perform the text Normalization on data selected based on state and perform below steps, 
*	Convert the text into lower case
*	Remove  unwanted spaces
*	Remove unwanted characters in the word
*	Tokenize the text

### Text Vectorization:
In this step we performed the text vectorization for both Input text and the capabilities of the manufacturer using the TFIDF Vectorizer.
#### TFIDF Vectorizer:
TF-IDF stands for "Term Frequency -- Inverse Document Frequency". This is a technique to quantify a word in documents.

> TF-IDF = Term Frequency (TF) * Inverse Document Frequency (IDF)

Term Frequency:
The term frequency of a word in a document is calculated by counting the number of instances a word appears in a document / total no of words in document.

> tf(t,d) = count of t in d / number of words in d.\
> t =  word in document\
> d = Document

 Inverse Document Frequency:
The Inverse Document Frequency of a word is calculated by taking the total number of documents, dividing it by the number of documents that contain a word, and calculating the logarithm.

> idf(t) = loge (N/(df ))\
> t =  word in document \
> N =  Total number of documents\
> df = Number of documents that contain a word

### Calculating the Similarity Score using Cosine Similarity:

In this step we calculate the similarity score between the Input and the capabilities of each manufacturer using the cosine similarity matrix.

#### Cosine Similarity:
Cosine similarity is the measure of similarity between two vectors, by computing the cosine of the angle between two vectors projected into multidimensional space. It can be applied to items available on a dataset to compute similarity to one another via keywords or other metrics. Similarity between two vectors (A and B) is calculated by taking the dot product of the two vectors and dividing it by the magnitude value as shown in the equation below. We can simply say that the CS score of two vectors increases as the angle between them decreases.
Formula for calculating the cosine similarity

![CS](https://github.com/PurushothamVadde/Manufacturers-Recommendation-System-With-Natural-Language-Processing/blob/master/images/Picture1.png)

Top 10 Companies with high similarity score:
| company_score  |  ID   |
| :------------- | :-----| 
|    0.445438    | 381   |
|    0.429004    | 318   |
|    0.425167    | 445   |
|    0.390867    | 463   |
|    0.386685    | 546   |
|    0.375450    | 428   |
|    0.365071    | 690   |
|    0.362529    | 611   |
|    0.353399    | 47    |
|    0.353399    | 1302  |


### Results:

Based on the Similarity score we will display the manufacturers as suggested manufactures to the user for the entered capabilities, in or case the below companies are the suggested companies for input  ("COVID-19 Response")
![Results](https://github.com/PurushothamVadde/Manufacturers-Recommendation-System-With-Natural-Language-Processing/blob/master/images/Picture2.png)
### Conclusion:
By this Model we can recommend the Manufacturing Company that is near to the user based on the requirement of the user with high Accuracy.


