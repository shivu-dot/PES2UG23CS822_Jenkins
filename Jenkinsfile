pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/shivu-dot/PES2UG23CS822_Jenkins.git'
            }
        }
        stage('Build') {
            steps {
                sh 'g++ main/hello.cpp -o output'  // Correct command
                sh 'rm nonexistentfile.txt'  // Intentional error (file doesn't exist)
            }
        }
        stage('Test') {
            steps {
                sh './output'
            }
        }
    }
    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
