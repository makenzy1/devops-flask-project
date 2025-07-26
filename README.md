# 🚀 DevOps Flask Project

This project demonstrates a complete DevOps workflow using a simple Python Flask application. It covers essential concepts including application development, containerization with Docker, and CI/CD automation using GitHub Actions.

---

## 📌 Project Overview

A basic Flask web application that returns **"Hello DevOps!"** at the root endpoint (`/`). The goal of this project is to serve as a beginner-friendly DevOps pipeline example — taking an application from code to container to deployment-ready image on Docker Hub.

---

## 🧰 Tech Stack

- **Language**: Python 3
- **Web Framework**: Flask
- **Containerization**: Docker
- **CI/CD**: GitHub Actions
- **Registry**: Docker Hub

---

## 📂 Project Structure

```
devops-flask-project/
│
├── .github/workflows/
│   └── docker-publish.yml   # GitHub Actions CI/CD workflow
│
├── app.py                  # Flask application
├── Dockerfile              # Docker image build config
├── .dockerignore           # Docker build context ignore rules
├── .gitignore              # Git ignore rules
├── README.md               # Project documentation
├── requirements.txt        # Python dependencies (optional)
└── venv/                   # Python virtual environment (ignored)
```

---

## ⚙️ Setup Instructions

> These steps assume you're using Windows PowerShell and have Python, Git, and Docker installed.

### Clone the repository

```powershell
git clone https://github.com/macpherson03/devops-flask-project.git
cd devops-flask-project
```

### Set up a Python virtual environment

```powershell
python -m venv venv
.\venv\Scripts\Activate.ps1
```

### Install Flask

```powershell
pip install flask
```

### Run the application

```powershell
python app.py
```
Visit [http://127.0.0.1:5000](http://127.0.0.1:5000) in your browser to see the message:

    Hello DevOps!

### Docker Instructions

**Build the Docker image:**
```powershell
docker build -t macpherson03/devops-flask:latest .
```

**Run the Docker container:**
```powershell
docker run -p 5000:5000 macpherson03/devops-flask:latest
```
Access the app at: [http://localhost:5000](http://localhost:5000)

**Push the image to Docker Hub (after logging in):**
```powershell
docker login
docker push macpherson03/devops-flask:latest
```

### CI/CD with GitHub Actions

The project includes a GitHub Actions workflow located at `.github/workflows/docker-publish.yml` that automates:

- Docker image build
- Docker Hub login using secrets
- Docker image push to your Docker Hub repository

### Setup Required

In your GitHub repository:

1. Go to **Settings > Secrets and variables > Actions > New repository secret**
2. Add the following secrets:

    | Name            | Description                  |
    |-----------------|-----------------------------|
    | DOCKER_USERNAME | Your Docker Hub username     |
    | DOCKER_PASSWORD | Your Docker Hub access token |

Once set up, every push to the main branch will trigger an automated Docker build and push.

### Test CI/CD

To test CI/CD:

1. Modify any file (e.g., add a comment to `app.py`)
2. Commit and push to the main branch:

    ```powershell
    git add .
    git commit -m "Test CI/CD workflow"
    git push origin main
    ```
3. Check the **Actions** tab in your GitHub repo to monitor the build and push process.

### 🙌 Contributing

Contributions are welcome! To suggest a change:

1. Fork the repository
2. Create a feature branch:
    ```powershell
    git checkout -b feature-name
    ```
3. Commit your changes
4. Push to your fork and submit a pull request

### 📄 License

This project is licensed under the MIT License.

### ✉️ Contact

- **Maintainer:** Macpherson Nwoko
- **Docker Hub:** [@macpherson03](https://hub.docker.com/u/macpherson03)
- **GitHub:** [@makenzy1](https://github.com/makenzy1)

### 📦 Docker Hub Image

🔗 [View Image on Docker Hub](https://hub.docker.com/r/macpherson03/devops-flask)

