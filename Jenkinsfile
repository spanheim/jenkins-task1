
pipeline {
    agent any
    environment {
        APP_PORT = '9090'
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Unit Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Check Test Running') {
            steps {
                script {
                    // Output log file content to check if "RestIT" is mentioned there
                    sh 'cat /local/jenkinsHome/jobs/job/builds/1/log'
                    // Check for "RestIT" in the log
                    sh 'grep -q "Running com.softserve.verify.RestIT" /local/jenkinsHome/jobs/job/builds/1/log || exit 1'
                }
            }
        }
    }
}
