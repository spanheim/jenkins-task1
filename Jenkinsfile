pipeline {
    agent any
    environment {
        APP_PORT = '9090'  // Set the environment variable APP_PORT to 9090
    }
    stages {
        stage('Build') {
            steps {
                // Use the maven package phase to build the project
                script {
                    echo "Building the project on port ${APP_PORT}"
                }
                sh 'mvn clean package'
            }
        }
        stage('Unit Test') {
            steps {
                // Use the maven test phase to run unit tests
                script {
                    echo "Running unit tests"
                }
                sh 'mvn test'
            }
        }
    }
}
