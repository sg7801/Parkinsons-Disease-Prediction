# Parkinson's Disease Prediction Using Microsoft Azure
In this project, we have used the Parkinson's Disease Dataset that contains the biomedical voice measurements of various people. Hence, we seek to predict if a person has the disease or not by using two algorithms. The result will be binary, i.e. "0" for healthy and "1" for those with disease. We will comparing the accuracy of Hyperdrive Run with tuned hyperparameters and AutoML Run on Microsoft Azure. After comparing the performances of both algorithms, we deploy the best performing one.

![Diagram](https://user-images.githubusercontent.com/61888364/103487129-08036d00-4e29-11eb-9419-a63e83287971.png)

## Dataset Overview
The dataset was created by Max Little of the University of Oxford, in collaboration with the National Centre for Voice and Speech, Denver, Colorado, who recorded the speech signals. The original study published the feature extraction methods for general voice disorders.

Parkinson's Disease is a brain disorder that targets the nervous system of human body. This results in tremors, stiffness and disturbs or slows the movement. When the nerve cell damage in the brain cause the dopamine levels to go down, it leads to Parkinson's. Immediate medication can help to control symptoms.

It is a multivarite dataset that contains the range of biomedical voice measurements of 31 people, out of which 23 had Parkinson's disease. Each column is itself a voice measure and rows correspond to 195 voice recordings from those individuals.

### Citation: 
Exploiting Nonlinear Recurrence and Fractal Scaling Properties for Voice Disorder Detection', Little MA, McSharry PE, Roberts SJ, Costello DAE, Moroz IM. BioMedical Engineering OnLine 2007, 6:23 (26 June 2007)

### Task:
Since, its a classification task with binary output, the column "status" will be used to determine if a person is healthy, denoted by "0" or is having Parkinson's disease, denoted by "1". 

### Attributes:
- **Matrix column entries (attributes):**<br>
- **name** - ASCII subject name and recording number <br>
- **MDVP:Fo(Hz)** - Average vocal fundamental frequency<br>
- **MDVP:Fhi(Hz)** - Maximum vocal fundamental frequency<br>
- **MDVP:Flo(Hz)** - Minimum vocal fundamental frequency<br>
- **MDVP:Jitter(%),MDVP:Jitter(Abs),MDVP:RAP,MDVP:PPQ,Jitter:DDP** - Several measures of variation in fundamental frequency<br>
- **MDVP:Shimmer,MDVP:Shimmer(dB),Shimmer:APQ3,Shimmer:APQ5,MDVP:APQ,Shimmer:DDA** - Several measures of variation in amplitude<br>
- **NHR,HNR** - Two measures of ratio of noise to tonal components in the voice<br>
- **status** - Health status of the subject (one) - Parkinson's, (zero) - healthy<br>
- **RPDE,D2** - Two nonlinear dynamical complexity measures<br>
- **DFA** - Signal fractal scaling exponent<br>
- **spread1,spread2,PPE** - Three nonlinear measures of fundamental frequency variation<br>

### Access to the dataset:
Since the dataset was available in ASCII CSV format, therefore it has been provided in this repository itself at : https://github.com/sg7801/Parkinsons-Disease-Prediction/blob/main/parkinsons.txt 

## Automated ML Run

Firstly, We used the TabularDatasetFactory to create a dataset from the provided link and then used the clean_data function to clean the data. Then we split the train and test sets and upload them to datastore. Then, we define the task as Classification with accurcay as primary metric and 5 n-cross validations. 
Below are the settings along their defination and reasons why we chose them for our AutoML Run:


