# nexedge-test-app
DOCKER COMMANDS
# build docker container image
docker build -t test-app .

# list docker images with the tag version
docker images

# run the docker image locally
docker run testapp

# tag the image so it can be pushed to container registry (artifact registry)
docker tag test-app artifact-rule/app-name:tag-version
Example:
docker tag test-app europe-west3-docker.pkg.dev/xxxl-cloud-eng-gcp/test-repo/test-app:latest
Note: Please replace the place holder url with yours
# push docker image to artifact registry
docker push europe-west3-docker.pkg.dev/xxxl-cloud-eng-gcp/test-repo/test-app:latest


KUBERNETES COMMANDS
# connect to kubernetes cluster via the kubectl command
gcloud container clusters get-credentials abel-cluster --zone us-central1-c --project project-abel-440217
Note: please replace cluster details with yours

# list the nodes in a k8s cluster
kubectl get nodes

# list the namespaces in your cluster
kubectl get ns

# apply the deployment manifest which contains your container (docker) image
kubectl apply -f deployment.yaml

# apply the service manifest
kubectl apply -f service.ayml

# apply the ingress manifest
kubectl apply -f ingress.yaml

# list or get the deployment which manages your pods where your image is running
kubectl get deployments

# get or list the pods where your container image runs
kubectl get pods

# describe a pod. Useful for troubleshooting
kubectl describe pods POD_NAME 

# get the service
kubectl get service

# get the ingress
kubectl get ingress
