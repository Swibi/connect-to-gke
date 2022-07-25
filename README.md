# Connect to GCP
A composite action for easy setup and connection to a gke cluster running on the Google Cloud Platform. 

# Usage

Simply include the following step in your GitHub action to connect to a GKE cluster, and set the GitHub secrets according to the instructions give by the actions used within this composite:

``` yaml
- name: Connect to GKE
  uses: 'Swibi/connect-to-gke'
  with:
    GCP_SA_KEY: ${{ secrets.GKE_SA_KEY }}
    GCP_PROJECT_ID: ${{ secrets.GKE_PROJECT }}
    GKE_CLUSTER: <your-cluster-name>
    GKE_ZONE: <your-cluster-zone>
```

The description for the various values are as follows: 
* GCP_SA_KEY
    * Service Account Key JSON (see: https://github.com/google-github-actions/auth)
* GCP_PROJECT_ID
    * GCP Project ID (see: https://github.com/google-github-actions/setup-gcloud)
* GKE_CLUSTER:
    * GKE cluster to be connected to (check in GCP console, under Kubernetes Engine to get the cluster name
* GKE_ZONE: 
    * GKE zone/location, where the cluster is hosted (can be found next to cluster name)