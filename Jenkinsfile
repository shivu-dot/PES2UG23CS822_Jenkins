pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
                sh 'ls -R'  // Debugging step to check file locations
            }
        }

        stage('Build') {
            steps {
                sh 'g++ main/hello.cpp -o output'  // Correct path
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }
    }
}
