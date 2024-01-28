# conductor-oss-helm-chart

## How to run Conductor locally
---
#### Setup
You need to Minikube or Kind cluster running on your local or dev environment

Links
- https://github.com/conductor-oss/conductor
- https://conductor-oss.org/
- https://docs.conductor-oss.org/devguide/concepts/index.html
- https://docs.conductor-oss.org/documentation/api/index.html


### Install conductor
```
helm install conductor conductor-k8s-helm-chart/
helm upgrade conductor conductor-k8s-helm-chart/
```

### Port Forward the ports for conductor UI and Swagger UI


##### Conductor UI
```
k port-forward svc/conductor 5000:5000
```

##### Swagger UI
```
k port-forward svc/conductor 8080:8080
```

### To execute a new workflow 

Send a POST request to http://127.0.0.1:5000/api/workflow

with a payload of 
```
{
  "name": "<workflow name>"
}
```
if you have a workflow already created named "http" send the payload as below as a POST request

```
{
  "name": "http"
}
```
