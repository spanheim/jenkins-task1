pipeline {
    agent any
    environment {
        APP_PORT = '9090' 
    }
    stages {
        stage('Build') {
            steps {
                
                script {
                    echo "Building the project on port ${APP_PORT}"
                }
                sh 'mvn clean package'
            }
        }
        stage('Unit Test') {
            steps {
                
                script {
                    echo "Running unit tests"
                }
                sh 'mvn test'
            }
        }
    }
}
