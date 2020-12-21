Human activity recognition plays a significant role in human-to-human interaction and interpersonal relations. Because it provides information about the identity of a person, their personality, and psychological state, it is difficult to extract. The human ability to recognize another person's activities is one of the main subjects of study of the scientific areas of computer vision and machine learning.The experimental results show that our method can significantly improve classification, interpretation, and retrieval performance for the video images. The novelty of this paper is twofold. First to capture the video images of human. Secondly, to identify the different types of action performed by human.
The dataset can be obtained here – https://deepmind.com/research/open-source/kinetics
→ The dataset has 700 labels where each of the label signifies a particular human action. There are approximately 6.5L YouTube videos labelled accordingly and these videos are clipped to 10 seconds. 
→ The final dataset contains 100 videos – 10 videos for each of the 10 categories after sampling.
→ The videos were captured at a frame rate of 5fps and each frame was down-sampled to the resolution of 128 x 128 pixels.

We would finally get a 5-dimensional tensor of shape (<number of videos>,<number of frames>,<width>,<height>,<channels>).
  
DEPLOYMENT:
Step 1: Taking input 
Input is in the form of link of YouTube video (Max 10 sec).
Input will be taken from html form connected to flask as backend.
The link will be stored as string in variable.

Step 2: Extracting Video and Tensors 
The link will be the sent to module named make_tensors.py.
Where it will be passed through the script where the video gets extracted and saved in current directory.
Then the path of the video will be given to the module named utils.py, where the read_video method will generate the tensors and store it in variable.

Step 3: Making Prediction 
After we got the tensors, we import our model (final_model.h5).
We feed the tensors to model and make predictions and store it in variable.
Then we extract the activity name using data frame of targets that we imported earlier and pass it to main app.

Step 4: Showing prediction to user 
After we got the predictions and activity name, we give argument to the render template method where replace the answer holding variable.


