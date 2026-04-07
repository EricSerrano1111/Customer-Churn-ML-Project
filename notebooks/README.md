# Telco Customer Churn Models

## Description
Telco is attempting to predict customer churn with the use of existing company data. Dataset feature examples include Tenure, Monthly Charges, service subscription details as well as some customer demographic info. Models were engineered to predict if customers were expected to leave or cancel their existing services with the Telco organization. The program language used to create the models is Python along with various libraries such as Scitkit-Learn, Pandas, and Numpy. A pipeline is utilized with Scikit-Learn to create reproducible experiments and MLflow is utilized to track as well as record the various model training runs.

## Getting Started

### Dependencies:
* Python 3.13.5
* Scikit-Learn
* Pandas
* SciPy
* Seaborn & Matplotlib
* Current Web Browser
* Jupyter Notebook
* MLflow

### Installing
* **Anaconda:** [https://www.anaconda.com/download](https://www.anaconda.com/download) (Python, Scikit-Learn & Jupyter Notebook)
* **Pandas:** [https://pandas.pydata.org/pandas-docs/stable/getting_started/install.html](https://pandas.pydata.org/pandas-docs/stable/getting_started/install.html)
* **MLflow:** [https://mlflow.org/docs/latest/getting-started/index.html](https://mlflow.org/docs/latest/getting-started/index.html)

### Executing Program
1. To Start MLflow, go to anaconda prompt and execute the following:
   mlflow server --backend-store-uri sqlite:///mlflow.db --default-artifact-root file:///C:/temp/mlflow/artifacts

2. Open your browser and go to http://localhost:5000 for MLflow UI.

3. Once MLflow is running, open a new anaconda prompt and execute:
    jupyter notebook

### Program Setup Reference
Terminal 1: The Server
1. Open Anaconda Prompt.
2.	Change directory: cd ‘path/to/your/project_folder’ (if needed)
3.	Start MLflow: mlflow server --backend-store-uri sqlite:///mlflow.db --default-artifact-root file:///C:/temp/mlflow/artifacts
4.	Minimize window.

Terminal 2: The IDE
1.	Open a 2nd Anaconda Prompt.
2.	Change directory: cd ‘path/to/your/project_folder’ (if needed) 
3.	Launch IDE: jupyter notebook 

### Expected Results
Once the first experiment or code blocks have been run, go to http://localhost:5000 and press the Experiments tab on the left-hand side in the MLflow user interface. That is where this project or experiment will appear in the dashboard similar to the below example:

![Dashboard](/images/png1.png)

Clicking on the name of this Experiment will bring you to an Overwiew page. On the Overview page, look at the left-hand side options and press Training runs. Doing so will bring you to the below:

![Overview](/images/png2.png)
 
Here you will be able to see logged information for each model’s training run along with the scoring metrics used for the experiment similar to the following example:

![Log Details](/images/png3.png)
 
Pressing on one of the models followed by the Artifacts button will bring you a detailed view of the model, environment, and library details such as the example below:

![Artifacts](/images/png4.png)

## Help / Issue Log
1. MLflow UI not displaying runs 
* Symptom: The MLflow dashboard at localhost:5000 was empty despite models running successfully in Jupyter.
* Resolution: The MLflow server was looking at a database, but the notebook was defaulting to a local mlruns folder. Added mlflow.set_tracking_uri("http://localhost:5000") to the notebook to explicitly route the data to the active server.

2. Windows URI formatting error 
* Symptom: Running the MLflow server command mlflow server --backend-store-uri 'C:/temp/mlflow/localserver' produced a protocol error pointing at the ‘C’ drive.
* Resolution: Windows requires explicit URI prefixes. Changed the command to sqlite:///C:/temp/mlflow/localserver.db and removed the single quotes.

3. Deleted runs preventing new experiments
* Symptom: Received an Exception: Run with UUID ... is already active error when attempting to iterate through models.
* Resolution: A previous interrupted run was hanging open in Jupyter's memory. Executed a while mlflow.active_run(): mlflow.end_run() loop and restarted the Jupyter kernel to clear the active state.
 
## TODO
* Incorporate the data type corrections into the pipeline 
* Automate it to run multiple times based on a list of different experimental parameters 
* Fine tune the models to enhance the AUC score

## Authors
* Lead Developer – **Eric Serrano**

## Version History
* 0.1 – Initial Release


## License
The MIT License (MIT) 
Copyright (c) 2026 Eric Serrano 
Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:
The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.



