## Day 6: Kubernetes Deployment & Service

### Overview
In this session, we worked on creating a **Deployment** and **Service** in Kubernetes. The Deployment ensures that the desired number of pods are always running, while the Service exposes the deployment to the external world. We also explored configuring different types of services like Load Balancer and ClusterIP.

### Steps to Create Deployment and Service

#### Creating Deployment

To create a deployment, define it in a YAML file and apply it using `kubectl`.

**YAML file (jeevitha-deployment.yaml):**
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: jeevitha-deployment
  namespace: jeevitha
spec:
  replicas: 5
  selector:
    matchLabels: 
      app: ipl
  template:
    metadata:
      labels:
        app: ipl
    spec:
      containers:
        - name: c-1
          image: daviddocker526/ipl-srh:latest
          ports:
            - containerPort: 80


### Service and Scaling

Once the deployment is created, expose it using a **Service**. In this case, a **LoadBalancer** service is used to allow external access to the application.

You can scale the deployment by modifying the `replicas` value in the deployment YAML file, which changes the number of pods.

### Summary
- **Deployment**: Ensures the desired number of pods are running.
- **Service**: Exposes your application to the outside world.
- **Scaling**: Modify the replicas value to scale the number of pods.
- **Load Balancer**: Used in the service to balance traffic across multiple pods.

