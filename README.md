The Deployment of Service tier and Backend tier is using Google Kubernetes Engine (GKE) service in Google Cloud platform

Link For Code Repository - https://github.com/vinays0409/kub-demo

Service tier - Docker Hub Image URL - https://hub.docker.com/r/vinay0409/nagp-api
Database tier - Docker Hub Image URL - https://hub.docker.com/_/postgres

URL for Service API tier to view the records from backend tier - http://34.122.126.89/items
Note: The above mentioned url uses the external endpoint for Service tier Loadbalancer service. If it does not work its because the cluster is stopeed on GCP. Kindly contact me in case required.

Note: Run the below convenience url once after deploying database and service tier to initialise database with data.
URL to initialse and preload the data in database - http://34.122.126.89/setupdb