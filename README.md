#Kubernetes Project: Nginx Frontend with Flask Backend

This project demonstrates a basic full-stack application deployed on a **Kubernetes Cluster (AWS)** using:

- **Flask** as the backend API (Python)
- **Nginx** as the frontend server (HTML + JS)
- Kubernetes **Deployments**, **Services**, and **Pods**
- Container images built using **Docker** and hosted on DockerHub

---

## 📁 Project Structure

├── backend/
│ ├── app.py
│ ├── requirements.txt
│ └── Dockerfile
├── frontend/
│ ├── index.html
│ ├── nginx.conf
│ └── Dockerfile
├── k8s/
│ ├── flask-deployment.yaml
│ ├── flask-service.yaml
│ ├── nginx-deployment.yaml
│ └── nginx-service.yaml


---

## 🚀 Live Demo

Once deployed, the application serves:

- A web page via Nginx (port 80)
- A backend `/api` endpoint that returns a JSON response

---

## 🔧 Prerequisites

- Docker
- kubectl
- Access to a Kubernetes Cluster (e.g., AWS EKS)
- A container registry (e.g., DockerHub)

---

## 🛠️ Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>


cd backend
docker build -t <your-dockerhub-username>/flask-app:latest .
docker push <your-dockerhub-username>/flask-app:latest

cd ../frontend
docker build -t <your-dockerhub-username>/nginx-frontend:latest .
docker push <your-dockerhub-username>/nginx-frontend:latest

# Deploy to Kubernetes
cd ../k8s
kubectl apply -f flask-deployment.yaml
kubectl apply -f flask-service.yaml
kubectl apply -f nginx-deployment.yaml
kubectl apply -f nginx-service.yaml

# Access the Application

kubectl get svc nginx-service

📚 Learnings & Concepts Covered
Kubernetes Resources: Pods, Deployments, Services

Service-to-service communication using ClusterIP

Docker image creation and deployment

YAML configuration management

Accessing services via LoadBalancer

💡 Future Enhancements
Add Ingress Controller for better routing

Use Helm Charts for packaging

Enable HTTPS via cert-manager

Add CI/CD with GitHub Actions or Jenkins

🤝 Contributing
Contributions, suggestions, and improvements are welcome. Fork the repo and submit a PR!

👤 Author
Satyakiran Padamati
📧 Email: satyapadamati5@gmail.com
🔗 LinkedIn: https://linkedin.com/in/satyakiranpadamati






