# BANSAM
## Introduction
### Overview
### Problem Statement
### Objective
## Dataset
### Variable
| ID  | City       | Temperature (°C) | Humidity (%) | Pressure (hPa) | Wind Speed (m/s) | Wind Direction (°) | Rain | Snow | Cloudiness (%) | Visibility (m) | Description    | Condition Type | Timestamp           |
|-----|------------|------------------|--------------|----------------|------------------|--------------------|------|------|----------------|----------------|----------------|----------------|---------------------|
| 3   | Samarinda  | 24.38            | 93           | 1010           | 1.54             | 200                | 0    | 0    | 72             | 10000          | broken clouds  | Clouds         | 2024-10-25 13:09:08 |
| 4   | Samarinda  | 24.41            | 93           | 1011           | 1.32             | 201                | 0    | 0    | 55             | 10000          | broken clouds  | Clouds         | 2024-10-25 14:09:08 |
| 5   | Samarinda  | 24.34            | 92           | 1010           | 1.47             | 207                | 0    | 0    | 60             | 10000          | broken clouds  | Clouds         | 2024-10-25 15:09:08 |

For the full dataset, [click here](dataset.csv).
### Preprocessing Steps
1. Separating Data <br>
   in this step we separate the data based on the `rain` column whose value is greater than 0
2. Labelling <br>
   after that we labelled the data with some considerations
3. Oversampling  <br>
   Next, since the data is skewed, we apply oversampling using the `SMOTE` technique
   
### EDA
![corr matrix](https://github.com/user-attachments/assets/8bb78d19-90e4-45fd-b713-9b0367d4306a)

from the correlation matrix above, there are several pairs of columns with values close to 1 (related):
- Wind Speed & Temperature
- Rain & Condition Type
- Rain & Description
- Cloudiness & Description
- Description & Condition Type

![pie](https://github.com/user-attachments/assets/79c2323f-8804-4d68-a2d2-bdf0f7a31156)

The 'aman' category is the most dominant with a percentage of 87.6%, followed by the 'waspada' category with a value of 7.9%, and the 'bahaya' category which has the smallest percentage of 4.5%.



## Model
### Architecture
### Performance Metrics
### Results
