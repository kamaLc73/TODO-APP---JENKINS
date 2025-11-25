pipeline {
    agent any

    stages {
        stage('Test Python') {
            steps {
                bat "\"C:\\Users\\kamal\\AppData\\Local\\Programs\\Python\\Python312\\python.exe\" --version"
                bat "\"C:\\Users\\kamal\\AppData\\Local\\Programs\\Python\\Python312\\Scripts\\pip.exe\" --version"
            }
        }

        stage('Install') {
            steps {
                bat "\"C:\\Users\\kamal\\AppData\\Local\\Programs\\Python\\Python312\\Scripts\\pip.exe\" install pytest fastapi sqlalchemy httpx"
            }
        }

        stage('Test App') {
            steps {
                bat "\"C:\\Users\\kamal\\AppData\\Local\\Programs\\Python\\Python312\\python.exe\" -m pytest test_app.py -v"
            }
        }
    }

    post {
        success {
            echo 'BUILD REUSSI!'
        }
    }
}
