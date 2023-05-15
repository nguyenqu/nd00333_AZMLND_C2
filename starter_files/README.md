# Operationalizing Machine Learning

This project consists of two parts:<br>
1. The first part consists of creating a production machine learning model using AutoML in Azure Machine Learning Studio, and then deploying the best model and consuming 
it using the Swagger UI using the REST API endpoint and the key created for the deployed model.<br>
2. The second part of the project follows the same steps, but this time Azure Python SDK is used to create, train, and publish a pipeline with Jupyter Notebook. 
The whole procedure is explained in this README file and the result is demonstrated in the screencast video.<br>

For both parts of the project, I use the dataset available here, which contains marketing data about people. 
The data refer to direct marketing campaigns by a Portuguese banking institution. 
The classification objective is to predict whether the customer will subscribe to a bank term deposit. 
The result of the prediction appears in column **_y_** and it's either **_yes_** or **_no_**.

## Architectural Diagram
The figure below shows steps that will be implemented in this project:

![Architecture](screenshots/Architecture.PNG)

## Key Steps

### 1. Authentication

- This is the important step to ensure secure and authentic access. Authentication is required to create the service principal account and associate it with a specific workspace.
- I am using the provided lab Udacity to complete this project. 
So I skipped this step because I don't have permission to create a security principal.

### 2. Automated ML Experiment

- We create the new Automated ML Run Experiment and then upload the [bank marketing dataset](https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv). <br>
- We run the experiment by configuring a new compute cluster, using classification and making sure best model explanation is enabled.

#### Registered Dataset
![](screenshots/1_0_Bankmarketing_Dataset_available.PNG)
![](screenshots/1_1_Bankmarketing_Dataset.PNG)
![](screenshots/2_2_Dataset.PNG)
![](screenshots/2_3_Dataset.PNG)
![](screenshots/2_4_Dataset.PNG)
![](screenshots/2_5_Dataset.PNG)
![](screenshots/2_6_Dataset.PNG)
![](screenshots/2_7_Dataset.PNG)
![](screenshots/2_8_Dataset.PNG)
![](screenshots/2_9_Dataset.PNG)
![](screenshots/2_10_Dataset.PNG)
![](screenshots/2_10a_Dataset.PNG)
![](screenshots/2_11_Dataset.PNG)
![](screenshots/2_12_Dataset.PNG)
![](screenshots/2_13_Dataset.PNG)
![](screenshots/2_14_Dataset.PNG)
![](screenshots/2_15_Dataset.PNG)
![](screenshots/2_16_Dataset.PNG)
![](screenshots/2_17_Dataset.PNG)
![](screenshots/2_18_Dataset.PNG)
![](screenshots/2_19_Dataset.PNG)
![](screenshots/2_20_Dataset.PNG)
![](screenshots/2_21_Dataset.PNG)
![](screenshots/2_22_Dataset.PNG)

#### AutoML Experiment Completed
![](screenshots/2_0_Experiment_completed.PNG)

#### Best Model
![](screenshots/2_1_Best_model.PNG)


### 3. Deploy the Best Model

- After completing the AutoML run, we get our best model. <br>
- Then we will deploy this model using **Azure Container Instance** (**ACI**) and enable **Authentication** to prevent unauthorized access.

![](screenshots/3_0_Deploy_Model.PNG)
![](screenshots/3_1_Top4_Feature.PNG)
![](screenshots/3_2_Top4_Feature.PNG)
![](screenshots/3_3_Metrics.PNG)
![](screenshots/3_4_Metrics.PNG)
![](screenshots/3_5_Accuracy_Precision.PNG)
![](screenshots/3_6_Accuracy_ROC.PNG)
![](screenshots/3_7_Accuracy_Calibration.PNG)
![](screenshots/3_8_Accuracy_Lift.PNG)
![](screenshots/3_9_Accuracy_Cumulativ_Gains.PNG)
![](screenshots/3_10_Confusion_matrix.PNG)

### 4. Enable Logging

- After deployment, we enable the Application Insights from the deployed model. <br>
- This helps us create log output using the Python SDK. <br>
- It plays a crucial role in debugging problems in production environments.

#### Logs from logs.py script
![](screenshots/5_0_Logs.PNG)
![](screenshots/5_1_Logs.PNG)

#### Application Insights Enabled
![](screenshots/4_Application_Insights.PNG)

### 5. Swagger Documentation

- Swagger helps us build, document, and consume RESTful web services. <br>
- It also explains what kind of requests the API can handle like **POST** and **GET**.

![](screenshots/6_0_Swagger.PNG)
![](screenshots/6_1_Swagger.PNG)

#### Default Swagger page
![](screenshots/6_2_Swagger.PNG)

#### Swagger Model Documentation
![](screenshots/6_3_Serve.PNG)
![](screenshots/6_4_Serve.PNG)
![](screenshots/6_5_Serve.PNG)
![](screenshots/6_6_Serve.PNG)
![](screenshots/6_7_Serve.PNG)

### 6. Consume Model Endpoints

- We need to use the provided service to get the data using an **HTTP request**. <br>
- It helps us validate data by determining if something has a problem or is wrong.

#### Endpoint.py output (Consuming Model Endpoints)
![](screenshots/7_0_Endpoints.PNG)
![](screenshots/7_1_Endpoints.PNG)

#### Benchmark output
![](screenshots/8_0_Benchmark.PNG)
![](screenshots/8_1_Benchmark.PNG)

### 7. Create and Publish a Pipeline

- The last and the most vital step is to make the model publically available. <br>
- This is done by **creating** a pipeline and then **publishing** it. <br>
- It is synonymous to Automation as the pipeline create ways for other services to interact with it using **HTTP endpoint**.

#### Created Pipeline and Pipeline Overview 
![](screenshots/9_0_Pipeline.PNG)

#### Pipeline Endpoint
![](screenshots/9_1_Pipeline_endpoint.PNG)

#### Bankmarketing Dataset with AutoML
![](screenshots/10_Bankmarketing_Dataset_AutoML.PNG)

#### Published Pipeline Overview
![](screenshots/12_Published_Pipeline_Overview.PNG)

#### Status Active
![](screenshots/11_REST_Endpoint_Active.PNG)

#### Running Pipeline
![](screenshots/13_Schedule_Run.PNG)

#### Run Widget - RunDetails Widget (Bild)
![](screenshots/14_0_Use_RunDetails_Widget.PNG)
![](screenshots/14_1_Use_RunDetails_Widget.PNG)
![](screenshots/14_2_Use_RunDetails_Widget.PNG)

## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:

## Standout Suggestions
*TODO (Optional):* This is where you can provide information about any standout suggestions that you have attempted.
