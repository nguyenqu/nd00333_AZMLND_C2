# Operationalizing Machine Learning

This project consists of two parts:<br>
1. The first part consists of creating a production machine learning model using AutoML in Azure Machine Learning Studio, and then deploying the best model and consuming 
it using the Swagger UI using the REST API endpoint and the key created for the deployed model.<br>
2. The second part of the project follows the same steps, but this time Azure Python SDK is used to create, train, and publish a pipeline with Jupyter Notebook. 
The whole procedure is explained in this README file and the result is demonstrated in the screencast video.<br>

For both parts of the project, I use the dataset available here, which contains [marketing data](https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv) about people. 
The data refer to direct marketing campaigns by a Portuguese banking institution. 
The classification objective is to predict whether the customer will subscribe to a bank term deposit. 
The result of the prediction appears in column **_y_** and it's either **_yes_** or **_no_**.

## Architectural Diagram
The figure below shows steps that will be implemented in this project:

![Diagramm](screenshots/Architecture.PNG)

### 1. Authentication

- This is the important step to ensure secure and authentic access. Authentication is required to create the service principal account and associate it with a specific workspace.

### 2. Automated ML Experiment

- We create the new Automated ML Run Experiment and then upload the bank marketing dataset. <br>
- We run the experiment by configuring a new compute cluster, using classification and making sure best model explanation is enabled.

### 3. Deploy the Best Model

- After completing the AutoML run, we get our best model. <br>
- Then we will deploy this model using **Azure Container Instance** (**ACI**) and enable **Authentication** to prevent unauthorized access.

### 4. Enable Logging

- After deployment, we enable the Application Insights from the deployed model. <br>
- This helps us create log output using the Python SDK. <br>
- It plays a crucial role in debugging problems in production environments.

### 5. Swagger Documentation

- Swagger helps us build, document, and consume RESTful web services. <br>
- It also explains what kind of requests the API can handle like **POST** and **GET**.

### 6. Consume Model Endpoints

- We need to use the provided service to get the data using an **HTTP request**. <br>
- It helps us validate data by determining if something has a problem or is wrong.

### 7. Create and Publish a Pipeline

- The last and the most vital step is to make the model publically available. <br>
- This is done by **creating** a pipeline and then **publishing** it. <br>
- It is synonymous to Automation as the pipeline create ways for other services to interact with it using **HTTP endpoint**.

## Key Steps
*TODO*: Write a short discription of the key steps. Remeber to include all the screencasts required to demonstrate key steps. 
### Step 1: Authentication
I am using the provided lab Udacity to complete this project. 
So I skipped this step because I don't have permission to create a security principal.

### Step 2: Automated ML Experiment

### Step 3: Deploy the Best Model

### Step 4: Enable Logging

### Step 5: Swagger Documentation

### Step 6: Consume Model Endpoints

### Step 7: Create and Publish a Pipeline


*TODO* Remeber to provide screenshots of the `RunDetails` widget as well as a screenshot of the best model trained with it's parameters.

## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:

## Standout Suggestions
*TODO (Optional):* This is where you can provide information about any standout suggestions that you have attempted.
