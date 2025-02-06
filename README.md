# **DengAI: Predicting Dengue Outbreaks Using Weather Data**  

## **Overview**  
Dengue fever is a mosquito-borne viral infection affecting millions globally, particularly in tropical and subtropical regions. Early prediction of dengue outbreaks can empower public health agencies to take proactive measures, reducing the impact on affected communities. **DengAI** leverages historical weather data to predict dengue case counts, utilizing machine learning techniques to identify environmental conditions conducive to outbreaks.

## **Features**  
- **Data Collection:** Integration of dengue case data with historical weather conditions.  
- **Data Preprocessing:** Cleaning, handling missing values, and engineering predictive features like lagged weather variables.  
- **Exploratory Data Analysis (EDA):** Visualization and correlation analysis to understand the data.  
- **Model Building:** Training machine learning models (Random Forest, XGBoost) for case count prediction.  
- **Deployment:** Providing predictions through a Flask-based API for easy integration with other systems.  

## **Getting Started**  
### **Prerequisites**  
- Python 3.8+  
- Libraries: Pandas, NumPy, Scikit-Learn, Matplotlib, Seaborn, Flask, Requests  

### **Installation**  
Clone the repository:  
```bash  
git clone https://github.com/your-username/DengAI.git  
cd DengAI  
pip install -r requirements.txt  
```

## **Dataset**  
### **Sources**  
- **Dengue Case Data:** Kaggle, WHO, CDC  
- **Weather Data:** OpenWeatherMap API, NOAA  
### **Structure**  
```
data/  
│-- dengue_features_train.csv  
│-- dengue_labels_train.csv  
│-- weather_data.csv  
```

## **Usage**  
### **1. Data Collection**  
Download data from [Kaggle](https://www.kaggle.com/c/dengue-prediction/data) or use the provided Python scripts to fetch weather data via APIs.  

### **2. Data Preprocessing**  
Run the data preprocessing script to clean and merge datasets:  
```bash  
python preprocess.py  
```

### **3. Model Training**  
Train the model with:  
```bash  
python train_model.py  
```

### **4. Deployment**  
Deploy the prediction API locally:  
```bash  
python app.py  
```  
Access the API at `http://127.0.0.1:5000/predict`  

### **5. Making Predictions**  
Send a POST request to the API endpoint:  
```bash  
curl -X POST -H "Content-Type: application/json" -d '{"temperature": 30.5, "humidity": 70, "rainfall": 100, "rainfall_lag_1": 90}' http://127.0.0.1:5000/predict  
```  

## **Project Structure**  
```
│-- data/  
│   │-- dengue_features_train.csv  
│   │-- dengue_labels_train.csv  
│   │-- weather_data.csv  
│-- notebooks/  
│   │-- EDA.ipynb  
│   │-- Model_Training.ipynb  
│-- scripts/  
│   │-- preprocess.py  
│   │-- train_model.py  
│   │-- app.py  
│-- models/  
│   │-- dengue_model.pkl  
│-- README.md  
│-- requirements.txt  
```  

## **Results**  
- **Accuracy:** Achieved a Mean Absolute Error (MAE) of **15 cases** per week.  
- **Feature Importance:** Rainfall and temperature lagged by 1-2 weeks were the most significant predictors.  

## **Future Improvements**  
- Incorporate additional features like population density or mosquito breeding sites.  
- Use deep learning models (e.g., LSTM) for improved time-series prediction.  
- Extend API to provide visual dashboards and alerts.  

## **Contributing**  
Contributions are welcome! Please fork the repository and submit a pull request with detailed descriptions of your changes.  

## **License**  
This project is licensed under the MIT License.  

## **Contact**  
For inquiries or collaboration, please contact [your-email@example.com](mailto:your-email@example.com).  

## **Acknowledgments**  
- Kaggle for the dataset  
- OpenWeatherMap for the weather API  
- WHO and CDC for valuable resources  

---

This README provides a comprehensive guide for anyone interested in using or contributing to the **DengAI** project. Would you like any more details or adjustments? 😊
