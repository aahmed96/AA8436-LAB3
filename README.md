# AA8436-LAB3

This README goes through how the notebook runs. Basically, it is a python notebook so you can sequentially run all the cells on any platform (Google Colab or Jupyter Notebook). If running on Jupyter, you might have to install some packages that come pre-installed with google colab.

**Data Collection and Model Loading:**
The data was collected from the Google Drive Folder provided in the LAB3 manual. It was simply downloaded and is stored locally in the directory (/content) when you run the notebook on Colab. In addition, the github repo provided was cloned and the model and model weights were loaded directly from this directory. 

**Repaired Models:**
Three models were prepared via pruning. The steps have been detailed in the notebook and the corresponding PDF file also lists the process of pruning along with the graph detailing Clean Test Accuracy and Attack Success Rate as a funciton of chanels pruned (2%, 4% and 10% models).

**GoodNet:**
The GoodNet was constructed rather simply. A function was created that takes in the Repaired Model, Bad Model and the path to the testing data. Then, it predicts and stores the predicitons from both models in separate arrays. After that, we iterate through the two predictions arrays and append to correct predictions if the predictions match. If they don't match, the prediction is appended to BadImages array. Along with the prediction labels, the index for the specific image is also stored so that the image can be easily retreived if need be.

**Comments on whether Pruning works:**
For this, pruning does not seem to work very well. As can be seen from the attack success rate, even with penalizing our clean accuracy by 10%, the attack success rate still lingers around 70%. Further pruning might decrease the attack success rate BUT it comes at the cost of lowering the model accuracy on clean images. This obviously defeats the purpose of classification model. Therefore, we must come up with a defence mechanism that lowers the attack success rate while maintaining a respectable accuracy on clean images.

