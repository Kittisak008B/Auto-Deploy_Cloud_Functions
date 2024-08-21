
<h1> Auto-Deploy_Cloud_Functions </h1> 
<p align="center">
  <img src="./pics/a000.png" width="800"> <br>
  overview
</p>

<h2> 1) Create Cloud Scheduler job, Pub/Sub topic, dataset and table in BigQuery </h2>
<p>
  <img src="./pics/a01.png" width="400"> 
  <img src="./pics/a02.png" width="400"> <br>
  <img src="./pics/a03.png" width="600"> <br>
  <p> create the dataset and table successfully </p> <br>
  <img src="./pics/a04.png" width="400"> 
  <p> set the schedule to have Cloud Pub/Sub execute every 5 minutes </p>
  <img src="./pics/a05.png" width="400"> 
  <p> create the Pub/Sub topic </p> 
  <img src="./pics/a06.png" width="400"> 
  <img src="./pics/a07.png" width="700"> 
  <p> create cloud scheduler job successfully </p> <br>
</p>

<h2> 2) Create workflow in the GitHub repository </h2>

<h2> 3) Create a Service Account for connecting GitHub Actions with Google Cloud </h2>
<p>
  <img src="./pics/c01.png" width="400"> 
  <p> This service account has the role to deploy Cloud Functions </p> <br>
  <img src="./pics/c02.png" width="700"> 
  <p> create a private key for the service account </p>
  <img src="./pics/c03.png" width="400"> 
  <p> Grant the App Engine default service account permission to use the github-action-service-account </p>
  <img src="./pics/c04.png" width="400"> 
  <p> Grant the Compute Engine default service account permission to use the github-action-service-account </p>
</p>

<h2> 4) Create secret in the repository </h2>
<p>
  <img src="./pics/d01.png" width="200"> 
  <p> GCP_PROJ_NAME -> Project ID <br>
      GCP_CREDENTIALS -> base64-encoded of the private key </p>
</p>

$`cat private_key_file_name.json|base64 -w 0`

<h2> 5) Push code to the main branch to run the workflow </h2>

<h2> Reference </h2>
https://github.com/google-github-actions/deploy-cloud-functions <br>
https://github.com/fonylew/simple-cloud-functions-to-bigquery

