### Vehicle Damage Detection App
This app allows you drag and drop an image of a car and it will tell you what kind of damage it has. The model is trained on 3/4 th "front & rear views" of a car. So, the picture should capture in the same view. 

![UI_Screen.png](UI_Screen.png)

### Model Details
1. Used CNN (Convolutional Neural Network). This is good at processing images. 
2. Used RestNet50 for transfer Learning
3. Model was trained on 1725 images with 6 target classes 
#### Six Target classes along with sample image
| 1.Front Normal                    | 2.Front Crushed                    | 3.Front Breakage                   |
|-----------------------------------|------------------------------------|------------------------------------|
| <img src="FN_3.jpg" width="200"/> | <img src="FC_43.jpg" width="200"/> | <img src="FB_15.jpg" width="200"/> |
<br>
| 4.Rear Normal                      | 5.Rear Crushed                     | 6.Rear Breakage                   |
|------------------------------------|------------------------------------|-----------------------------------|
| <img src="RN_10.jpg" width="200"/> | <img src="RC_15.jpg" width="200"/> | <img src="RB_2.jpg" width="200"/> |

The Accuracy on Validation-set (Test-dataset) was around 81.57%


### Setup 
1.  To get started, first install the dependencies using

      ```commandline
      pip install -r requirements.txt
      ```

   2. Run the stearmlit app
      go to respective folder 
   
      ``` commandline
      run streamlit run main.py"
      ```
### Damage Prediction 
![Uploaded_image.png](Uploaded_image.png)

### Model Creation & Evaluation steps
![data_flow_and_model_evaluation_1.png](data_flow_and_model_evaluation_1.png)

### Core Model ( Architecture ) 
![cnn_resnet50_architecture_v1.png](cnn_resnet50_architecture_v1.png)

### Steps involved in Core Model 
![core_model_steps.png](core_model_steps.png)

### Some interesting predictions
#### Scenario-1 
![Scenario_1_flat_front.png](Scenario_1_flat_front.png)
Though, we provided flat front, it predicted well.

Takeaway:- 
1.  May be "features" involved in identifying "Front Normal" works well. Still, we have to try with similar images and make sure, it works fine or not :-)


#### Scenario-2
![Scenario_2_RB_Mother_and_Kid.png](Scenario_2_RB_Mother_and_Kid.png)
This image is perfect "Rear Normal", but it was predicted as "Rear Breakage"
    
Takeway:- 
1.  As a humans, we know Mother and Kid sitting at Rear side of the car. But Model considers "that portion of the pixel" as "Breakage"
2. Good thing is, it predicted well, the first part as "Rear"
3. Generally, if someone want to assess the damage, "Only car should be there. No passengers or No other objects". 
