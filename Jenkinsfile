pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'g++ main.cpp -o output'  // Compile C++ file
                echo 'Build Stage Successful'
            }
        }
        stage('Test') {
            steps {
                sh './output'  // Run compiled C++ file
                echo 'Test Stage Successful'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deployment Successful'
            }
        }
    }
    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
