# FastAPI Todo App with Jenkins Demo

This project is a simple Todo application built with FastAPI, containerized with Docker, and automated using Jenkins.

## Features
- REST API for managing todos
- SQLite database
- Simple frontend (HTML/CSS)
- Automated CI/CD pipeline with Jenkins

## Project Structure
```
Dockerfile
Jenkinsfile
requirements.txt
test_app.py
app/
  database.py
  main.py
  models.py
  static/
    index.html
    style.css
```

## How to Run
1. **Build Docker image**
   ```
   docker build -t fastapi-todo .
   ```
2. **Run the container**
   ```
   docker run -d -p 8000:8000 --name fastapi-todo fastapi-todo
   ```
3. **Access the app**
   - API: http://localhost:8000
   - Frontend: http://localhost:8000/static/index.html

## Jenkins Pipeline
The Jenkins pipeline (see `Jenkinsfile`) automates:
- Dependency installation
- Testing (`test_app.py`)
- Docker build & run

## Requirements
- Python 3.12+
- Docker
- Jenkins

## License
MIT
