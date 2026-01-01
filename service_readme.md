# create service.yaml

echo "" > service.yaml

# Enter the following content
apiVersion: v1
kind: Service
metadata:
    name: streamlit
spec:
    selector:
        app: pod-app
    ports:
    - port: 8080
      targetPort: 8080

#start the service
kubectl apply -f service.yaml

# check if it working
kubectl get svc

# expose the service to the host with minikube
minikube service streamlit
