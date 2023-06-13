# MLOps Zoomcamp following online on [Global MLOps Zoomcamp](https://github.com/DataTalksClub/mlops-zoomcamp)
MLOps Zoomcamp  


# Starting Jupyter Notebook remotely on port 9999
- `jupyter notebook --port=9999` 9999 because my local Anaconda is using the default Jupyter port 8888

# Starting MLFlow...
- `mlflow server -h 0.0.0.0 -p 5000 --backend-store-uri postgresql://postgres:<master-password>@joreyes-mlops-backend-store.ctrfy31kg8iq.ap-southeast-2.rds.amazonaws.com:5432/ --default-artifact-root s3://joreyes-mlflow-artifacts-store` This is a server with S3 as the artifact root (need accesskey and secret)
- `mlflow server -h 0.0.0.0 -p 5000 --backend-store-uri postgresql://postgres:<master-password>@joreyes-mlops-backend-store.ctrfy31kg8iq.ap-southeast-2.rds.amazonaws.com:5432/` This is a server with the EC2 instance itself as the artifact store
- the command above will start the MLFlow server on port 5000 of the EC2 instance, connect to the specified backend store uri (which we configured earlier in Postgres), then connect also to our specified artifact store in S3
- MLFlow will then be available for use: http://ec2-<ip address like so: 13-236-208-102>.ap-southeast-2.compute.amazonaws.com:5000/
- or configured with VSCode port forwarding at port 5000 so that you can easily: http://127.0.0.1:5000/

