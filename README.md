# Cloud Run Secrets
Simple Cloud Run secrets example using Go and Secrets Manager in GCP. 

Pull down repo

Setup gcloud with `gcloud auth login`

Create two secrets 

`echo -n "This is my name" | gcloud secrets versions add myname --data-file=-`

`echo -n "This is my secret message" | gcloud secrets versions add mysecretmessage --data-file=-`

Deploy to Cloud Run

```
gcloud run deploy go-example --source . --region us-central1 --allow-unauthenticated --set-secrets=NAME=myname:latest,MSG=mysecretmessage:latest
```

