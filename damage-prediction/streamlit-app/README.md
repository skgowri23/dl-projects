### Vehicle Detection App
This app allows you drag and drop an image of a car and it will tell you what kind of damage it has. The model is trained on third quarter front and rear views hence the picture should capture the third quarter front or rear view of a car.

![Third_qtr_of_a_car.jpg](Third_qtr_of_a_car.jpg)

### Model Details
1. Used RestNet50 for transfer Learning
2. Model was trained on 1725 images with 6 target classes 
   1. Front Normal![FN_3.jpg](FN_3.jpg)
   2. Front Crushed![FC_43.jpg](FC_43.jpg)
   3. Front Breakage![FB_15.jpg](FB_15.jpg)
   4. Rear Normal![RN_10.jpg](RN_10.jpg)
   5. Rear Crushed![RC_15.jpg](RC_15.jpg)
   6. Rear Breakage![RB_2.jpg](RB_2.jpg)
3. The Accuracy on Validation-Set was around 81.57%

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
### Architecture 
![CNN_Architecture_for_classification.png](CNN_Architecture_for_classification.png)