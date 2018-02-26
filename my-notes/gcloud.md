### Google Cloud Platform
#### Kubernetes introduction guide

First of all install cloud SDK
>https://cloud.google.com/sdk/docs/quickstarts

Set project & compute zone

```
gcloud config set project [PROJECT_ID]
gcloud config set compute/zone [COMPUTE_ZONE]
```

if you don't have cluster — create one
```
gcloud container clusters create [CLUSTER_NAME]
```

And get credentials for a cluster
```
gcloud container clusters get-credentials [CLUSTER_NAME]
```

kubectl create clusterrolebinding cluster-admin-binding \
--clusterrole cluster-admin --user $(gcloud config get-value account)
(remember to add defaultservice account to that group)

You are ready to go!
You now can use `kubectl` to manage cloud cluster
