# Pod
apiVersion: v1
kind: Pod
metadata:
 name: digi-pod
 labels:
  app: travel-app
spec:
 containers:
 - name: cont-1
   image: vaibhav3885/travel
   ports:
   - containerPort: 80
---
apiVersion: v1
kind: Service
metadata:
  name: travel-svc
spec:
  selector:
    app: travel-app
  ports:
  - protocol: TCP
    port: 80
    targetPort: 80
  type: ClusterIP
  
