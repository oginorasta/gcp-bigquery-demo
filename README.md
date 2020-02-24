# gcp-bigquery-demo
This is a repository showing how to use bigquery as an app datbase storing user credentials


## Background 
This is a write up for an upcoming Meetup and Medium post.

## Idea
BigQuery is a database made by Google and available on GCP.
This demo projects shows how easy it is to use BigQuery as a database for a backend app fo example to store user credentials.

## Architecture
There are GCP projects ```ogino-app-live``` and ```ogino-userdb-live```. In ```ogino-app-live``` a simple [GO app](https://go.dev/) is running in a VM with a service account which has access to the dataset _userdb_ in ```oghub-userdb-live```. The GO app uses the official [cloud.google.com/go/bigquery](cloud.google.com/go/bigquery) library to perform simple CRUD operations on the tables inside the _userdb_ database.

## Learnings
- Easy to spin up and test
- BigQuery is highly available and easy to use
- There are provided Google libraries 

### Useful gcloud commands for demoing
- git clone https://github.com/oginorasta/gcp-bigquery-demo.git
- cd gcp-bigquery-demo
- gcloud auth activate-service-account --key-file=oghub-userdb-live-bigquery-reader.json
- gcloud auth list
- bq ls --project ogino-userdb-live
