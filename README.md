# 🐍 Flask Hello World App

A minimal Python web application using [Flask](https://flask.palletsprojects.com/), containerized with Docker and ready for Kubernetes deployment. This project serves as a great starting point for cloud-native Python development using [Devfile](https://devfile.io/).

---

## 🚀 Project Overview

This application responds with `"Hello World!"` when accessed via its root route (`/`). It is configured to run in containerized environments and includes resources for building, deploying, and developing using modern tools like OpenShift Dev Spaces or Kubernetes.



## 📁 Project Structure

```
.
├── app.py               # Main Flask app
├── devfile.yaml         # Devfile spec for cloud-native development
├── deploy.yaml          # Kubernetes deployment and service configuration
├── requirements.txt     # Python dependencies
├── docker/
│   └── Dockerfile       # Docker image definition
├── .gitignore
├── LICENSE
└── README.md
```

## 🧪 Requirements

- Python 3.9+
- Docker
- Kubernetes (optional: Minikube, OpenShift, etc.)
- `pip` package manager



## ⚙️ Local Development

1. **Install dependencies:**

```bash
   pip install -r requirements.txt
````

2. **Run the app:**

   ```bash
   FLASK_PORT=8080 python app.py
   ```

3. **Visit in browser:**

   ```
   http://localhost:8080
   ```



## 🐳 Docker

### Build the Docker image:

```bash
docker build -t flask-hello-world -f docker/Dockerfile .
```

### Run the Docker container:

```bash
docker run -p 8081:8081 flask-hello-world
```



## ☸️ Kubernetes Deployment

1. **Ensure Docker image is available (either locally or in a registry).**

2. **Apply deployment:**

   ```bash
   kubectl apply -f deploy.yaml
   ```

3. **Access the service:**

   Depending on your cluster setup, use:

   ```bash
   kubectl port-forward service/my-python 8081:8081
   ```

   Then visit:

   ```
   http://localhost:8081
   ```



## 🧪 Devfile Support

This project includes a `devfile.yaml` for seamless integration with cloud IDEs like:

* [OpenShift Dev Spaces](https://docs.redhat.com/en/documentation/red_hat_openshift_dev_spaces/3.0)
* [Eclipse Che](https://www.eclipse.org/che/)

