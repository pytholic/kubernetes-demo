# Description

_A web app that interacts with MongoDB._

# References

[Kubernetes Docs](https://kubernetes.io/docs/home/)

[Kubernetes Crash Course for Absolute Beginners](https://www.youtube.com/watch?v=s_o8dwzRlu4&t=3826s&ab_channel=TechWorldwithNana)

# Steps

- Deploy MongoDB database
- Deploy Web Application
- External Configuration for DB URL and Credentials
  - Secret
  - ConfigMap
- Make Web Application accessible externally from the browser

# Notes

- Secret needs base64 values

```
echo -n <text> | base64
```

- Need to pass mongo db username and password from secret to the webapp
- NodePort Service is accessible on each Worker Node’s IP address

```
minikube start --driver docker
minikube status

kubectl apply -f mongodb-secret.yaml
kubectl apply -f mongodb-config.yaml
kubectl apply -f mongodb.yaml
kubectl apply -f webapp.yaml

kubectl get all
kubectl get service
minikube ip or kubectl get node -o wide
```

Combine ip and service port. Open in browser.
