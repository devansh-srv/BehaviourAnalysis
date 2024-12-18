# Realtime Behavior Analysis 
To assert a better feedback mechanism in a traditional classroom environment we propose using computer vision and machine learning techniques for real-time, objective analysis of student emotions and teacher behavior simultaneously Using a Combined model the two combined models are:
- **Facial Expression**
- **Body Language Classifier**


## Facial Expression
- Video capture using python CV.
- Uses Cascade Classifier to detect faces
- CNN then classifies the detected faces to predefined categories
  - Happy
  - Sleepy
  - Angry
  - Neutral
  - Fear
  <br>
  
  ### Flowchart:
    ![image](https://github.com/user-attachments/assets/ba47afab-65ad-48a0-9d7f-794e402018b4)

  ### Results:
  - Total params: 13,111,367
  - Trainable params: 13,103,431
  - Non-trainable params: 7,936
  - Accuracy:  88.64 %

  Loss function Used: **Categorical Cross-Entropy**
  
  ![unnamed](https://github.com/user-attachments/assets/cd3c5bc4-9de4-40ea-a487-d05346b5ff08)

## Body Language Classification
- Utilizes [MediaPipe Holistic](https://github.com/google/mediapipe/blob/master/docs/solutions/holistic.md) to classify body poses from video data into specific categories:
  - Writing
  - Active Explaining
  - Passive Explaining
  - At Desk

- Pose Estimation model was trained on lectures videos from MIT Open Course Ware.
- Frames from the video lectures were first converted to RGB format, Mediapipe holistic model was used to extract landmarks.
- Landmarks from 10 such frames were contacted then written to csv along with class name
- This data-set was then fed to a Random Forrest model to which classifies into the given categories.
- Next step was to create a composite model that incorporates both the models, leveraging the strengths of both models and providing a holistic view.

### Flowchart:
  ![image](https://github.com/user-attachments/assets/3da7f7dc-9a98-4352-9316-1035a7310ee3)

### Results:
  Model used: **Random Forrest** <br>
  Accuracy: 97.81 %

  ![Confusion Matrix](https://github.com/user-attachments/assets/b0d07dff-f5a2-44c5-b2b0-ed17362453c9)


<p float="left">
  <img src="/Project Images/Picture7.png" width="420" />
  <img src="/Project Images/Picture1.png" width="420" /> 
</p>

## Combined Results
Both Models were run simultaneously to give combined results

#### Detecting teacher’s behavior:
<p float="left">
  <img src="/Project Images/Picture4.png" width="420" />
  <img src="/Project Images/Picture5.png" width="420" /> 
</p>

#### Detecting students behaviour:
<img src="/Project Images/Picture6.png" />
