# BANSAM
## Introduction
### Overview
This model utilizes a Deep Neural Network to predict flood that could happen in Samarinda City. It includes 9 features to ensure accurate analysis and provides output in the form of probabilities across three labels: Safe, Alert, and Danger, helping the people in Samarinda City understand the level of flood risk effectively.
### Problem Statement
1. What are the main weather factors influencing “danger” conditions in Samarinda, such as rainfall, humidity, air pressure, or wind speed?
2. What type of weather conditions (condition_type) most often occur before, during, and after a flood, and how does the combination of humidity and air pressure affect visibility in each of these conditions?
3. How can data-driven insights improve community awareness and preparedness for flood risks in Samarinda?

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
   in this step we separate the data based on the `rain` column whose value is greater than 0.
2. Labelling <br>
   after that we labelled the data with some considerations.
3. Oversampling  <br>
   Next, since the data is skewed, we apply oversampling using the `SMOTE` technique.
   
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
![architecture](https://github.com/user-attachments/assets/96ae5eec-a9d9-43b9-b346-4361d596bdcc)

In this case, we use a DNN for our machine learning model, with 9 feature inputs, 1 normalization layer, 4 hidden layers, and 1 softmax output.
### Performance Metrics
![performance matrix](https://github.com/user-attachments/assets/4fb54cbe-515a-46e1-9339-dd876d64e9d3)
![accuracy](https://github.com/user-attachments/assets/79adace0-e659-42b5-9874-ac111590ad8d)

A significant improvement is observed around epoch 44, with the training accuracy reaching 95% and validation accuracy at 94%

### Results
![result](https://github.com/user-attachments/assets/0e8a6b22-c23f-4334-8bcd-4660aefee83e)

After completing the training, we made predictions using the existing model that had been exported with the most recent training data, and we obtained these results, with a total of 31 data points being mispredicted.
