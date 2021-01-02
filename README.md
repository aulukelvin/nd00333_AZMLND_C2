# Operational Machine Learning With Bank Marketing Dataset

This project is part of the Udacity Azure ML Nanodegree. In this project, our goal is to determine the next set of potential customers to which to market. 
The project involves working with the [Bank Marketing Dataset](https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv). To accomplish this task we are building a model then create consumable pipelines. It includes using Azure AutoML to select best model and most suitable data pre-processing steps, deploying it and then consuming the model through its API endpoints. The project also includes creating a fully operational Machine Learning pipeline, publishing it as well as consuming it using Azure Python SDK.

## Architectural Diagram
The architecural diagram explains the flow of the project in a pictorial represenation. We start with creating the Bankmarketing dataset from a CSV file. We then create an Azure AutoML model using ML Studio and deploy the best model from the run. After enabling authentication, we enable Application Insights to maintain the logs of our model. We then use swagger to document model API structure, and thereafter consume the endpoints. We can also use Apache Benchmark tool for benchmarking the response, though it is not mandatory. Lastly, we publish a ML Pipeline using Azure Python SDK. 
![alt text](https://github.com/aulukelvin/nd00333_AZMLND_C2/blob/master/UdacityMLOperationalED.jpg)


## Key Steps
#### 1. Registering the dataset in Azure ML Studio.<br></br>
Upload and register the bank marketing dataset to Azure ML studio datasets.
![alt text](https://github.com/aulukelvin/nd00333_AZMLND_C2/blob/master/Registered_datasets.PNG)
<br></br>

#### 2. Creating the AutoML Model on the given dataset.<br></br>
Then, using Azure AutoML service, create an AutoML model that has to be deployed later. Use an existing compute, or create a new one. Increase the minimum number of nodes available to 1 and run the experiment. 
![alt text](https://github.com/aulukelvin/nd00333_AZMLND_C2/blob/master/Experiment_completed.PNG)
<br></br>

#### 3. The best model chosen by AutoML.<br></br>
After the experiment completed, AutoML will summarize the task with the best performance, in our case the accuracy, and the best model, in our case, the best perfoming model is is VotingEnsemble model. As the name suggested, VotingEnsemble model is a second level model built on top of other simpler models. It ran last and gives marginal better result than simple models.
Deploy this model from ML Studio. Remember to choose ACL as the hosting option and choose enable authentication.

#### 4. Run the logs.py script to observe the logs.<br></br>
Write the code to enable application insights in the logs.py file and run the file. Observe the logs it provides of the deployed model.
![alt text](https://github.com/aulukelvin/nd00333_AZMLND_C2/blob/master/logs.PNG)
<br></br>

#### 5. Enable Application Insights for logging.<br></br>
You can see that the Application Insights which was earlier set to false, is now enabled.
![alt text](https://github.com/aulukelvin/nd00333_AZMLND_C2/blob/master/ApplicationInsightEnabled.PNG)
<br></br>

#### 6. Run the serve.py and swagger.sh files on localhost.<br></br>
Next we are going to use the swagger tool, which is a documentation and API structuring tool. For this we need Docker to be installed on the system as we need to download the container. Once docker is installed, run serve.py and swagger.sh file as shown.
The swagger will be hosted locally on the port you have used in the above files.

#### 7. Swagger running on localhost.<br></br>
Since swagger is running locally now, we can see our model name as well as the API methods.
Here you can see model name and API methods GET and POST.
![alt text](https://github.com/aulukelvin/nd00333_AZMLND_C2/blob/master/swagger.PNG)
<br></br>

#### 8. Run the endpoint.py script to get JSON output from the model.<br></br>
The endpoint.py script sends a request to the deployed model via the POST API method and receives data in the form of JSON file which is displays. We have to set the scoring URI and the authentication key first. 
![alt text](https://github.com/aulukelvin/nd00333_AZMLND_C2/blob/master/Endpoint_consumption.PNG)
<br></br>

#### 9. Pipeline is running in the Azure ML studio's pipeline section.<br></br>
The pipeline created through Azure Python SDK is now running in the portal.
![alt text](https://github.com/aulukelvin/nd00333_AZMLND_C2/blob/master/running_pipeline.PNG)
<br></br>

#### 10. Pipeline endpoint after publishing it.<br></br>
This is the published pipeline's endpoint 
![alt text](https://github.com/aulukelvin/nd00333_AZMLND_C2/blob/master/pipeline_endpoint.PNG)
<br></br>

#### 11. Bank Marketing Dataset with AutoML module. <br></br>
![alt text](https://github.com/aulukelvin/nd00333_AZMLND_C2/blob/master/dataset_with_Automl.PNG)
<br></br>

#### 12. Published Pipeline overview showing REST endpoint and Active Status. <br></br>
The published pipeline status is ACTIVE now and the REST endpoint is also available.
![alt text](https://github.com/aulukelvin/nd00333_AZMLND_C2/blob/master/pipeline_endpoint.PNG)
<br></br>

#### 12. RunDetails Widget showing the step runs.  <br></br>
The pipeline runs have been completed.
![alt text](https://github.com/aulukelvin/nd00333_AZMLND_C2/blob/master/RunDetails.PNG)
<br></br>


## Screen Recording
Click [here]() to see the ScreenCast.
