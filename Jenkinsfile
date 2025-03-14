pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh '/usr/bin/mvn clean install' // Use the full Maven path
                echo 'Build Stage Successful'
            }
        }
        stage('Test') {
            steps {
                sh '/usr/bin/mvn test'
                echo 'Test Stage Successful'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deploy') {
            steps {
                sh '/usr/bin/mvn deploy'
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
