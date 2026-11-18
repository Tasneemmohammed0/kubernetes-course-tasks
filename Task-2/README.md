
# Task 2: FastAPI + MySQL on Kubernetes

## 1. Namespace, Secret & ConfigMap

Created the `webapp-stack` namespace, `mysql-secret` for database credentials, and `webapp-config` for application settings.

![Namespace, Secret and ConfigMap](screenshots/01-namespace-secret-configmap.png)

## 2. Persistent Storage

Created a 2Gi PersistentVolume (`mysql-pv`) and PersistentVolumeClaim (`mysql-pvc`) for MySQL data storage.

![Persistent Volume and Persistent Volume Claim](screenshots/02-storage.png.png)

## 3. MySQL Deployment

Deployed one MySQL replica with persistent storage and a ClusterIP Service on port `3306`.

![MySQL Pod Ready](screenshots/03-mysql-ready.png)

## 4. FastAPI Deployment

Deployed two FastAPI replicas connected to MySQL through Kubernetes Services.

![FastAPI and MySQL Deployments Ready](screenshots/04-app-ready.png)

## 5. Ingress Configuration

Enabled the Nginx Ingress Controller and configured `webapp-ingress` to route HTTP traffic to the FastAPI Service.

![Ingress Controller and Ingress Resource](screenshots/05-ingress-ready.png)

## 6. Guestbook Application

Accessed the FastAPI guestbook through the Ingress Controller at `http://localhost:8080`.

![Guestbook Application in Browser](screenshots/06-guestbook-browser.png)
