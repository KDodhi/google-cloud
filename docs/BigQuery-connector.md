# Google BigQuery Connection

Description
-----------
Use this connection to access data in Google BigQuery.

Properties
----------
**Name:** Name of the connection. Connection names must be unique in a namespace.

**Description:** Description of the connection.

**Project ID**: Google Cloud Project ID, which uniquely identifies a project. This is where the BigQuery job will be run
to query the data. It can be found on the Dashboard in the Google Cloud Platform Console. Make sure the service account
specified below has the permission to run BigQuery jobs in this project by granting the service account
the `BigQuery Job User` role.

**Dataset Project ID**: Google Cloud Project ID of the project where your dataset is. It can be found on the Dashboard
in the Google Cloud Platform Console. Make sure the service account specified below has the permission to view data in
this project by granting the service account the `BigQuery Data Viewer` role.

**Service Account**: When running on Google Cloud Platform, the service account key does not need to be provided, as
it can automatically be read from the environment. In other environments, the service account key must be provided.

* **File Path**: Path on the local file system of the service account key used for authorization. Can be set to '
  auto-detect' when running on a Dataproc cluster. When running on other clusters, the file must be present on every
  node in the cluster.

* **JSON**: Contents of the service account JSON file.

**Show Hidden Datasets:** Whether to show hidden datasets.

Path of the connection
----------------------
To browse, get a sample from, or get the specification for this connection through 
[Pipeline Microservices](https://cdap.atlassian.net/wiki/spaces/DOCS/pages/975929350/Pipeline+Microservices), the `path`
property is required in the request body. It can be in the following form :

1. `/{dataset}/{table}`
   This path indicates a table. A table is the only one that can be sampled. Browse on this path to return the specified table.

2. `/{dataset}`
   This path indicates a dataset. A dataset cannot be sampled. Browse on this path to get all the tables under this dataset.

3. `/`
   This path indicates the root. A root cannot be sampled. Browse on this path to get all the datasets visible through this connection.
