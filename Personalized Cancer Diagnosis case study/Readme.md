# It's time to change how the world treats cancer.

## Personalized Cancer Diagnosis Case Study


### Source / Usefull Links:

<p> Source: https://www.kaggle.com/c/msk-redefining-cancer-treatment/ </p>
<p> Data: Memorial Sloan Kettering Cancer Center (MSKCC)</p>
<p> Download training_variants.zip and training_text.zip from Kaggle.</p> 

<h6> Context:</h6>
<p> Source: https://www.kaggle.com/c/msk-redefining-cancer-treatment/discussion/35336#198462</p>

<h6> Problem statement : </h6>
<p> Classify the given genetic variations/mutations based on evidence from text-based clinical literature. </p>

**Some articles and reference blogs about the problem statement**

1. https://www.forbes.com/sites/matthewherper/2017/06/03/a-new-cancer-drug-helped-almost-everyone-who-took-it-almost-heres-what-it-teaches-us/#2a44ee2f6b25
2. https://www.youtube.com/watch?v=UwbuW7oK8rk 
3. https://www.youtube.com/watch?v=qxXRKVompI8


### Data Overview

- Source: https://www.kaggle.com/c/msk-redefining-cancer-treatment/data
- We have two data files: one conatins the information about the genetic mutations and the other contains the clinical evidence (text) that  human experts/pathologists use to classify the genetic mutations. 
- Both these data files are have a common column called ID
- <p> 
    Data file's information:
    <ul> 
        <li>
        training_variants (ID , Gene, Variations, Class)
        </li>
        <li>
        training_text (ID, Text)
        </li>
    </ul>
</p>



<h6>training_variants</h6>
<hr>
ID,Gene,Variation,Class<br>
0,FAM58A,Truncating Mutations,1 <br>
1,CBL,W802*,2 <br>
2,CBL,Q249E,2 <br>
...

<h6> training_text</h6>
<hr>
ID,Text <br>
0||Cyclin-dependent kinases (CDKs) regulate a variety of fundamental cellular processes. CDK10 stands out as one of the last orphan CDKs for which no activating cyclin has been identified and no kinase activity revealed. Previous work has shown that CDK10 silencing increases ETS2 (v-ets erythroblastosis virus E26 oncogene homolog 2)-driven activation of the MAPK pathway, which confers tamoxifen resistance to breast cancer cells. The precise mechanisms by which CDK10 modulates ETS2 activity, and more generally the functions of CDK10, remain elusive. Here we demonstrate that CDK10 is a cyclin-dependent kinase by identifying cyclin M as an activating cyclin. Cyclin M, an orphan cyclin, is the product of FAM58A, whose mutations cause STAR syndrome, a human developmental anomaly whose features include toe syndactyly, telecanthus, and anogenital and renal malformations. We show that STAR syndrome-associated cyclin M mutants are unable to interact with CDK10. Cyclin M silencing phenocopies CDK10 silencing in increasing c-Raf and in conferring tamoxifen resistance to breast cancer cells. CDK10/cyclin M phosphorylates ETS2 in vitro, and in cells it positively controls ETS2 degradation by the proteasome. ETS2 protein levels are increased in cells derived from a STAR patient, and this increase is attributable to decreased cyclin M levels. Altogether, our results reveal an additional regulatory mechanism for ETS2, which plays key roles in cancer and development. They also shed light on the molecular mechanisms underlying STAR syndrome.Cyclin-dependent kinases (CDKs) play a pivotal role in the control of a number of fundamental cellular processes (1). The human genome contains 21 genes encoding proteins that can be considered as members of the CDK family owing to their sequence similarity with bona fide CDKs, those known to be activated by cyclins (2). Although discovered almost 20 y ago (3, 4), CDK10 remains one of the two CDKs without an identified cyclin partner. This knowledge gap has largely impeded the exploration of its biological functions. CDK10 can act as a positive cell cycle regulator in some cells (5, 6) or as a tumor suppressor in others (7, 8). CDK10 interacts with the ETS2 (v-ets erythroblastosis virus E26 oncogene homolog 2) transcription factor and inhibits its transcriptional activity through an unknown mechanism (9). CDK10 knockdown derepresses ETS2, which increases the expression of the c-Raf protein kinase, activates the MAPK pathway, and induces resistance of MCF7 cells to tamoxifen (6). ... 



### Type of Machine Learning Problem : 

- There are nine different classes a genetic mutation can be classified into => Multi class classification problem


### Performance Metric(s):
Source: https://www.kaggle.com/c/msk-redefining-cancer-treatment#evaluation

Metric(s): 
* Multi class log-loss 
* Confusion matrix 

### Machine Learing Objectives and Constraints:

<p> Objective: Predict the probability of each data-point belonging to each of the nine classes.
</p>
<p> Constraints:
</p>
* Interpretability
* Class probabilities are needed.
* Penalize the errors in class probabilites => Metric is Log-loss.
* No Latency constraints.


### Spliting the data:
Split the dataset randomly into three parts train, cross validation and test with 64%,16%, 20% of data respectively

<hr>

<p style="background:black">
<code style="background:black;color:white">Step by Step Procedure i followed to achieve the target.
</code>
</p>

<hr>

- Understanding the Businessreal world problem

- Understanding Real-world/Business objectives and constraints.

- Understanding Data overview

- Mapping the real-world problem to an ML problem

- Defining Performance Metric as per the ML problem

- importing required libraries

- Reading the gene , variation and text data

- Exploratory Data Analysis

- Preprocessing text 

- splitting the data into train, test, cv

- ploting Distribution of y_i's in Train, Test and Cross Validation datasets

- Prediction using a 'Random' Model

- Univariate Analysis on gene feature

- Univariate Analysis on variation feature

 - Is the Text feature stable across all the data sets (Test, Train, Cross validation)?
 
- Conclusion - Univariate Analysis of Feature Engineering

- Stacking the three types of features (gene , variation and text)

- Apply Base Line Model(naive Bayes) to check the error and model performance , then  we can apply correct ML model on top of that.

 - Baseline Model - Hyper parameter Tuning
 
 - Testing the model using the best hyperparameter
 
 - ploting Confusion matrix
 
 - Feature Importance, Correctly classified point
 
 - Feature Importance, incorrectly classified point
 
- Apply KNN model

 - Hyper parameter Tuning
 
 - Testing the model using the best hyperparameter
 
 - ploting Confusion matrix
 
 - Sample Query point -1 and Sample Query point -2
 
- Apply Logistic Model - Class balancing

 - Hyper parameter Tuning
 
 - Testing the model using the best hyperparameter
 
 - ploting Confusion matrix
 
 - Feature Importance, Correctly classified point
 
 - Feature Importance, incorrectly classified point
 
- Apply Logistic Model - without Class balancing

 - Hyper parameter Tuning
 
 - Testing the model using the best hyperparameter
 
 - ploting Confusion matrix
 
 - Feature Importance, Correctly classified point
 
 - Feature Importance, incorrectly classified point
 
- Applt Linear Support Vector Machines

 - Hyper parameter Tuning
 
 - Testing the model using the best hyperparameter
 
 - ploting Confusion matrix
 
 - Feature Importance, Correctly classified point
 
 - Feature Importance, incorrectly classified point
 
- Apply Random Forest Classifier (With One hot Encoding - Response Coding)

 - Hyper parameter Tuning
 
 - Testing the model using the best hyperparameter
 
 - ploting Confusion matrix
 
 - Feature Importance, Correctly classified point
 
 - Feature Importance, incorrectly classified point
 
- Apply Random Forest Classifier (Without One hot Encoding)

 - Hyper parameter Tuning
 
 - Testing the model using the best hyperparameter
 
 - ploting Confusion matrix
 
 - Feature Importance, Correctly classified point
 
 - Feature Importance, incorrectly classified point
 
- Stack the models

 - Hyper parameter Tuning
 
 - Testing the model using the best hyperparameter
 
 - ploting Confusion matrix
 
 -  Maximum Voting classifier
 
- **Applying all the models with TFIDF-Features - Instead of using all the words in the dataset, use only the top 1000 words based of tf-idf values**

- Univariate analysis - gene Feature

 - How to featurize this Gene feature ? , How good is this gene feature in predicting y_i?
 
 - Univariate analysis - variation Feature
 
 - How good is this gene feature in predicting y_i? 
 
 - Univariate analysis - Text Feature
 
 - How good is this gene feature in predicting y_i?
 
- Q. Is the Text feature stable across all the data sets (Test, Train, Cross validation)?

- Apply ML models - Stacking the three types of features (gene , variation and Tex)

- Applly all the models along with hyperparmeter tuning , testing model , ploting confusion matrix, feature importance stpes


- **Logistic Regression with CountVectorizer(unigrams, bigrams)**

- Univariate Analysis on Gene Feature - CountVectorizer(unigrams , bi-grams)

- Univariate Analysis on Variation Feature - CountVectorizer(unigrams , bi-grams)

- Univariate Analysis on text Feature - CountVectorizer(unigrams , bi-grams)

- Normalize every feature and data preparation for ml models

- Stacking the three types of features (gene , variation and Tex)

- Apply Logistic Model - Class balancing

 - Hyper parameter Tuning
 
 - Testing the model using the best hyperparameter
 
 - ploting Confusion matrix
 
 - Feature Importance, Correctly classified point
 
 - Feature Importance, incorrectly classified point
 
- Apply Logistic Model - without Class balancing

 - Hyper parameter Tuning
 
 - Testing the model using the best hyperparameter
 
 - Ploting Confusion matrix
 
 - Feature Importance, Correctly classified point
 
 - Feature Importance, incorrectly classified point
 
- Observation on model performences (Conclusion)

- **Trying the feature engineering techniques discussed in the course to reduce the CV and test log-loss to a value less than 1.0**

- Univariate Analysis on Gene Feature - tfidfVectorizer(unigrams, bi-grams)

- Univariate Analysis on Variation Feature - tfidfVectorizer(unigrams, bi-grams)

- Univariate Analysis on text Feature - tfidfVectorizer(unigrams, bi-grams)

- Stacking the two types of features (gene and Text)

- Normalize every feature and data preparation for ml models

- Logistic Regression - With Class balancing Tfidf(bigrams) - Gene with Text

 - Hyper parameter Tuning
 
 - Testing the model using the best hyperparameter
 
 - Ploting Confusion matrix
 
 - Feature Importance, Correctly classified point
 
 - Feature Importance, incorrectly classified point
 
- Logistic Regression without class balancing - Tfidf- Gene, Text

 - Hyper parameter Tuning
 
 - Testing the model using the best hyperparameter
 
 - Ploting Confusion matrix
 
 - Feature Importance, Correctly classified point
 
 - Feature Importance, incorrectly classified point
 
- Observation on overall model performences (Conclusion)

- Ploting the performences by table format.

<hr>

- **I have keep in mind and didn't forget Our main objective : is to minimize the loss to lees than 1 , till the last line of code through out the steps .

<hr>


<a href="https://www.linkedin.com/in/rameshbattuai/">RAMESH BATTU</a>

