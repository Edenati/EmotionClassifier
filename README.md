# EmotionClassifier
## Introduction
This project aims to identify emotions in human videos using a deep learning-based approach. It classifys emotions into six universal emotions: happiness, sadness, fear, anger, neutral, and surprise. My method includes feature extraction, selection, and classification using Media-Pipe library and pre-trained neural networks. This algorithm uses the DenseNet201 architecture for the eyes and a Convolutional Neural Network (CNN) for the lips. The final result is determined by combining the predictions from both models.The system will classify the emotion for a given frame according to the emotion that received the highest accuracy from both models. It analyzed the proportion of success of each model, and weighted them accordingly.
## Data -Set 
The code includes two  functions that assist in creating a dataset consisting of images of eyes and lips only, extracted from a labeled dataset of face images. These functions are designed to simplify the data preprocessing step, making it easier to work with a specific set of features for emotion recognition.
With the use of the aforementioned functions, it is possible to generate a customized dataset, which can be categorized into separate folders based on the specific emotion expressed in each image. This allows for efficient organization and streamlined access to the data, making it easier to work with and ultimately leading to better results in emotion recognition.
<img width="488" alt="image" src="https://user-images.githubusercontent.com/81075338/219954824-e1bdfd14-ad55-430a-ae3b-3da88063f34e.png">
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
