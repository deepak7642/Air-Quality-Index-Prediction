# Air-Quality-Index-Prediction

### Organized by - DataVerse (12-hr ML Hackathon) of Cognizance IIT Roorkee
---

**Objective:** Predict the Air Quality Index (AQI) using pollutant and meteorological data.

**Evaluation Metrics:** Root Mean Squared Error (RMSE).

---

**Dataset Information :-** The dataset contains 9358 instances of hourly averaged responses from an array of 5 metal oxide chemical sensors embedded in an Air Quality Chemical Multisensor Device. The device was located on the field in a significantly polluted area, at road level,within an Italian city. Data were recorded from March 2004 to February 2005 (one year)representing the longest freely available recordings of on field deployed air quality chemical sensor devices responses. Ground Truth hourly averaged concentrations for CO, Non Metanic Hydrocarbons, Benzene, Total Nitrogen Oxides (NOx) and Nitrogen Dioxide (NO2) and were provided by a co-located reference certified analyzer. Evidences of cross-sensitivities as well as both concept and sensor drifts are present as described in De Vito et al., Sens. And Act. B, Vol. 129,2,2008 (citation required) eventually affecting sensors concentration estimation capabilities. Missing values are tagged with -200 value.

**Attribute Information:**

* Date (DD/MM/YYYY)
* Time (HH.MM.SS)
* True hourly averaged concentration CO in mg/m^3 (reference analyzer)
* PT08.S1 (tin oxide) hourly averaged sensor response (nominally CO targeted)
* True hourly averaged overall Non Metanic HydroCarbons concentration in microg/m^3 (reference analyzer)
* True hourly averaged Benzene concentration in microg/m^3 (reference analyzer)
* PT08.S2 (titania) hourly averaged sensor response (nominally NMHC targeted)
* True hourly averaged NOx concentration in ppb (reference analyzer)
* PT08.S3 (tungsten oxide) hourly averaged sensor response (nominally NOx targeted)
* True hourly averaged NO2 concentration in microg/m^3 (reference analyzer)
* PT08.S4 (tungsten oxide) hourly averaged sensor response (nominally NO2 targeted)
* PT08.S5 (indium oxide) hourly averaged sensor response (nominally O3 targeted)
* Temperature in Â°C
* Relative Humidity (%)

---

*Methodology for handling missing values and preprocessing:*  
We will drop rows and columns containing null values as they require significant transformations to properly structure the dataset. The preprocessing steps include:  
- Handling files with `';'` as a delimiter by specifying it as a parameter in the `read_csv` function.  
- Correcting values in the dataset that use commas instead of decimal points (e.g., `9,4` instead of `9.4`).  
- Defining relevant features and excluding those that may not contribute to the prediction. For example, the `date` column might not be directly helpful for predicting future values.  

---


For Modeling result - Random forest regression 
* MSE train: 0.006, test: 0.008
* RMSE train: 0.074, test: 0.090
* R^2 train: 1.000, test: 1.000
