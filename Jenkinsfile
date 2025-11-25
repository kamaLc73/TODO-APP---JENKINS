pipeline {
    agent any
    
    stages {
        stage('Install dependencies') {
            steps {
                bat 'pip install -r requirements.txt'
            }
        }
        
        stage('Test') {
            steps {
                bat 'pytest test_app.py --maxfail=1 --disable-warnings'
            }
        }
        
        stage('Build Docker image') {
            steps {
                bat 'docker build -t fastapi-todo .' 
            }
        }
        
        stage('Run Docker container') {
            steps {
                bat 'docker stop fastapi-todo || exit 0'
                bat 'docker rm fastapi-todo || exit 0'
                bat 'docker run -d -p 8000:8000 --name fastapi-todo fastapi-todo'
            }
        }
    }
    
    post {
        success {
            echo 'Build réussi! App disponible sur http://localhost:8000'
        }
        failure {
            echo 'Build échoué!'
        }
    }
}