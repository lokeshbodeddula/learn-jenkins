pipeline {
    agent any
    stages {
        stage('Build') {// Timeout counter starts AFTER agent is allocated
            steps {
                sh "This is Build"
            }
        }
        stage('Test') {
            steps {
                    sh "This is Test"
               
            }
        }
        stage('Deploy') {
            steps {
                sh "This is Deploy"
               
            }
        }
    }
}