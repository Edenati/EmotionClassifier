# EmotionClassifier
## Introduction
This project aims to identify emotions in human videos using a deep learning-based approach. It classifys emotions into six universal emotions: happiness, sadness, fear, anger, neutral, and surprise. My method includes feature extraction, selection, and classification using Media-Pipe library and pre-trained neural networks. This algorithm uses the DenseNet201 architecture for the eyes and a Convolutional Neural Network (CNN) for the lips. The final result is determined by combining the predictions from both models.The system will classify the emotion for a given frame according to the emotion that received the highest accuracy from both models. It analyzed the proportion of success of each model, and weighted them accordingly.
## Data -Set 
The code includes two  functions that assist in creating a dataset consisting of images of eyes and lips only, extracted from a labeled dataset of face images. These functions are designed to simplify the data preprocessing step, making it easier to work with a specific set of features for emotion recognition.
With the use of the aforementioned functions, it is possible to generate a customized dataset, which can be categorized into separate folders based on the specific emotion expressed in each image. This allows for efficient organization and streamlined access to the data, making it easier to work with and ultimately leading to better results in emotion recognition.
<img width="488" alt="image" src="https://user-images.githubusercontent.com/81075338/219954824-e1bdfd14-ad55-430a-ae3b-3da88063f34e.png">

## Training process 
It is important to note that during the training process, we noticed that each facial part behaves differently for different emotions. For example, the differences between angry and neutral expressions will be expressed in a change in the eyes appearance, while the position of the mouth stays pretty much the same in these emotions. And there is no doubt about the emotion that smiling lips represent. This is why we decided to give different weights in the final classification for different emotions that were classified from our models. for example if the CNN model (classifying emotions from lips images)has higher accuracy than the DenseNet model, it will have more weight in our final classification.Question: will you be able to identify which emotions this lips represents?

<img width="212" alt="image" src="https://user-images.githubusercontent.com/81075338/219958644-e9383292-3192-4370-8c0b-c4e494a2bff8.png">
     
The position of the mouth looks the same but nevertheless, they belong to people who experience different emotions. Here you can see the full images:

<img width="267" alt="image" src="https://user-images.githubusercontent.com/81075338/219958662-57f4ad87-23af-4de7-9e0b-9fda7e055b79.png">

         
Now when we are able to observe all of the facial expression we will be able to identify the left image as a neutral face and the right one as an angry face. The main difference between it reflects in the eyes expression. This is the confusion matrix we received from the CNN model. As was mentioned before CNN classifies the emotion based on lips images:

<img width="284" alt="image" src="https://user-images.githubusercontent.com/81075338/219958478-a086ebed-a542-47de-89c5-f2f88925e28b.png">

And this is the confusion matrix from DenseNet model (classifies the emotion based on eyes images):

<img width="324" alt="image" src="https://user-images.githubusercontent.com/81075338/219958491-c7d1c808-cfae-4bef-8fac-6627b39671e8.png">

We received these matrices that represent the results of each model classification that was performed on the testing data, as can be shown both of the modal classify emotions like neutral and happy with high accuracy, from the other hand it seems like Fear is more clearly visible in the changes of the lips patterns, while Sadness is more expressed in the changes of the eyes gaze.
### Final Result:
For the final result, we will use weighted Ensemble. Using this approach, the models are trained independently, and then their predictions are combined by taking a weighted average of the output probabilities, where the weight is determined by how well each model performed. This is why we gave in the final calculation more weight for the CNN classifications of fear and surprised and the Densenet received highest weights for anger and sadness. The system will classify the emotion for a given frame according to the emotion that received the highest accuracy from both models. We analyzed the proportion of success of each model, and weighted them accordingly. For example, for the emotion of fear, the model had a 60% success rate when analyzing the eyes and an 89% success rate when analyzing the lips. Therefore, we gave a higher weight to the lips (89/60 = 1.5) and used that weight in our final ensemble model for the emotion of fear. For emotions that have very small differences, such as happiness, where one model had a 90% success rate and the other had a 96% success rate, we did not assign a weight, as the difference is small and could be influenced by the data set used. Regarding the accuracy of the final model, it is difficult to compare it to the accuracy of the individual models because it operates on videos rather than images. However, the ensemble model achieved an estimated accuracy of 91% based on a small dataset of folders of videos of emotions.
## The system 
### workflow 
<img width="542" alt="image" src="https://user-images.githubusercontent.com/81075338/219954936-b91b738f-908f-422b-ab03-64dd25d9a72e.png">

### Product
<img width="437" alt="image" src="https://user-images.githubusercontent.com/81075338/219954987-224295c1-1450-4280-b58e-ef62b80021fa.png">

### Screens 
<img width="436" alt="image" src="https://user-images.githubusercontent.com/81075338/219955029-f8b5659f-8745-4508-a58d-4294436a56cd.png">

## User guide 
### Software Environment:
•	PyChram 
•	Python 3.8
### Python libraries that needed to be installed in order to execute the code:
•	Keras •	Media –pipe
•	Sklearn
•	Numpy
•	Os
•	Matplotlib
•	Seaborn
•	cv2
•	Shutil
•	Tkiner

*The input video must be mp4 type, for now, the system supports only these types of videos.

### General Description: 
The system is based on deep learning and is designed to classify human emotions from a given video. The system does not classify emotion with 100% accuracy, but can be used as a good base for future development. Every user can train the model by himself, with his own data set, most of the code is designed generically, so every user will be able to adjust his own data paths, size and unique information.
