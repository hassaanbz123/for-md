
# 20L-1365 (Hassaan Bin Zaid)
# 20L-1313 (Aroob Khalid)

# Personality-Prediction-Through-CV
A system that predict the personality of a person with OCEAN values and resume.

## Background of Personality Perception
The ***Big Five Personality Traits*** model is based on findings from several independent researchers, and it dates back to the late 1950s. But the model as we know it now began to take shape in the 1990s.
Lewis Goldberg, a researcher at the Oregon Research Institute, is credited with naming the model "*The Big Five*." It is now considered to be an accurate and respected personality scale, which is routinely used by businesses and in psychological research.
The Big Five Personality Traits Model measures five key dimensions of people's personalities:

### Openness 
>It sometimes called "Intellect" or "Imagination," this measures your level of creativity, and your desire for knowledge and new experiences.
### Conscientiousness
>This looks at the level of care that you take in your life and work. If you score highly in conscientiousness, you'll likely be organized and thorough, and know how to make plans and follow them through. If you score low, you'll likely be lax and disorganized.
### Extraversion/Introversion
>This dimension measures your level of sociability. Are you outgoing or quiet, for instance? Do you draw energy from a crowd, or do you find it difficult to work and communicate with other people?
### Agreeableness
>This dimension measures how well you get on with other people. Are you considerate, helpful and willing to compromise? Or do you tend to put your needs before others'?
### Natural Reactions
>Sometimes called "Emotional Stability" or "Neuroticism," this measure emotional reactions. Do you react negatively or calmly to bad news? Do you worry obsessively about small details, or are you relaxed in stressful situations?

### Possible Personalities that can be assigned:
- Dependable
- Responsible
- Serious
- Lively
- Extraverted

## Dependencies of System

- os: For accessing files and data from internal storage
- pandas: For accessing and manipulating data sheets
- numpy: For working on arrays
- tkinter: For building the GUI
- functools: For manipulating functions that operate on other functions
- pyresparser: For extracting information from resume
- sklearn: Classification/Regression/Clustering Algorithms. It helps the model to learn on various characteristics using logical reg
- nltk
- scaPy


## Description
The system built in this project predicts personality of peoples by using their gender, age, score of openness, conscientiousness, extraversion, agreeableness, neuroticism and experience. It parses all the data from CV/resume and on the result page, it shows all the information from the entered data and uploaded resume. This system uses logistic regression for training the model and pyresparser module for parsing the information from resume which is built using nltk and spaCy module in python.
Description of Methods and Flow in the System:

- ### train_model class 

>It contains two method which train the model and predict the result by giving the various values.
train method: It read the dataset for training the model from a csv file and build a model using Logistic Regression. It uses different 7 values for training the model.
test method: It predict the personality of a person by passing an array of values that contains gender, age and other 5 personality characteristics.

- ### main method

>We start with creating an object of train_model class and train the model by calling train method of class. Then we initialize a variable with Tk object and design the landing page of system using labels and button. A button with name Predict Personality is designed which calls predict_person¬ method. 


- ### predict_person method
> We withdraw the root tkinter window and create a new toplevel window and configure its size and attributes. We label the heading of window followed by various labels and their entries. For selecting of a resume file, user needs to press choose file button which then calls Openfile method that takes an argument of button. In predict_person method, various entries are taken for predicting the personality. Submit button pass all the values to prediction_result.

- ### OpenFile method
>It tries to open the directory with default address name and file types and except if file not chosen. After try except block, the method changes the name of choose file button in predict_person method with the base name of file so that user can know about the chosen file.
 
- ### prediction_result method 
>This method firstly closes the previous tkinter window which was used to take the data from user. After this, it calls test method of model object and stores the result returned by method. After this it parse all the information from resume and stores in a variable followed by a try except block which try to delete name and validate mobile number from fetched information from resume. Then it prints all the data submitted by user on console. After this, the method popup a full screen window which shows all the parsed information and predicted personality on GUI window along with the definition of each personality characteristic’s definition.

- ### check_type method

>It converts various strings and numbers into desired format and converts lists and tuples in string. 

### Limitations to CV Analysis

>Adversarial Attacks: CV systems can be vulnerable to adversarial attacks, where malicious actors deliberately manipulate or perturb the input data to mislead the model. Even subtle changes that are imperceptible to humans can cause significant misclassifications or false detections.
>Contextual Understanding and Common Sense: While CV models excel at recognizing and classifying objects, they often struggle with higher-level tasks that require contextual understanding or common sense reasoning. Extracting meaningful information from images in complex scenarios or understanding the relationships between objects can be challenging.
>Ethical and Bias Concerns: CV systems can inherit biases present in the training data, leading to discriminatory or unfair outcomes. For example, facial recognition algorithms have shown biases against certain demographic groups. Addressing these biases and ensuring ethical use of CV technology is a significant challenge.
>Computation and Resource Requirements: CV analysis often requires substantial computational power and resources, especially for large-scale deployments or real-time applications. Processing high-resolution images or video streams in real-time can be computationally expensive and may require specialized hardware or infrastructure.

## Note: CV datasets (Which includes the files that are read to detect the traits) have been gotten from kaggle.
### https://www.kaggle.com/datasets/gauravduttakiit/resume-dataset

