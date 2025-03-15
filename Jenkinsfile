pipeline {
    agent {
        docker {
            image 'node:14'
        }
    }
    stages {
        stage('Clone repository') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/shivu-dot/PES2UG23CS822_Jenkins.git'
            }
        }
        stage('Install dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Build application') {
            steps {
                sh 'npm run build'
            }
        }
        stage('Test application') {
            steps {
                sh 'npm test'
            }
        }
        stage('Push Docker image') {
            steps {
                sh 'docker build -t pes2ug23cs822/pes2ug23cs822:$BUILD_NUMBER .'
                sh 'docker push pes2ug23cs822/pes2ug23cs822:$BUILD_NUMBER'

            }
        }
    }
}
