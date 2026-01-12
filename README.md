💪 Body Fat Percentage Predictor



Machine learning model that predicts body fat percentage from simple body measurements. No expensive equipment needed, just a tape measure!


<img width="1920" height="852" alt="screenshot" src="https://github.com/user-attachments/assets/edc6e878-8f4f-4f2b-8a1c-673477a2dbd7" />







🎯 Problem



Traditional body fat measurement methods are expensive (DEXA: $50-150) or inconvenient (hydrostatic weighing). This tool provides free, instant predictions using machine learning.








📊 Dataset



252 samples with 13 body measurements (age, weight, height, body circumferences)



Target: Body fat percentage from underwater weighing



Cleaned to remove impossible values (e.g., 0% body fat) and outliers








🛠️ Approach







1. Data Cleaning







Removed physiologically impossible values (body fat <2% or >50%)



Applied IQR outlier detection



Excluded density feature (data leakage - directly calculates body fat)








2. Feature Engineering







BMI (Body Mass Index)



Waist-to-Hip Ratio



Chest-to-Abdomen Ratio



Age-Weight Interaction








3. Model Training



Evaluated 5 models (Linear, Ridge, Lasso, Random Forest, Gradient Boosting) with 5-fold cross-validation.



Best Model: Ridge Regression







Test R²: 0.739



Test MAE: 3.028



CV R²: 0.672716








4. Key Insights







Weight = strongest predictor



Model performs best for typical body types (15-25% body fat)



Ridge regularization prevented overfitting








💻 Tech Stack



Python • scikit-learn • pandas • Git




🚀 Quick Start



bash# Clone repo



git clone https://github.com/tosos24/body-fat-prediction.git



cd body-fat-prediction







# Install dependencies



pip install -r requirements.txt







Usage



Run the app locally with:



python app.py





Open the link displayed in your terminal to access the Gradio interface.



Select Quick Demo to try example profiles.



Select Manual Input to enter your own measurements.



The app outputs predicted body fat and the fitness category.






\\## 📁 Project Structure



```



├── app.py              # Gradio web app



├── data/



│   └── bodyfat.csv         # Dataset



├── model/



│   └── best\\\_model.pkl      # Trained model



├── notebooks/



│   ├── 01\\\_eda.ipynb        # Data exploration



│   ├── 02\\\_feature\\\_engineering.ipynb



│   └── 03\\\_modeling.ipynb   # Model training



├── requirements.txt



└── README.md








🔮 Future Work





Train separate models for men/women



Add confidence intervals



Computer vision for automated measurements from photos



Mobile app deployment








👤 Author



Ayeni OLuwatosin




ayenitosin39@gmail.com





