# create pod branch
git branch podyaml

# change to the dockerfile branch
git checkout podyaml

# create pod.yaml 
echo "" > pod.yaml

# Enter the following content

apiVersion: v1
kind: Pod
metadata:
  name : streamlit
  labels:
    app: pod-app
spec:
  containers:
  - name: streamlit
    image: {your user name}/myapp:latest


# start pod
kubectl apply -f pod.yaml

# check if it working
kubectl get pods

# check status
kubectl logs streamlit
or
kubectl describe pod streamlit
