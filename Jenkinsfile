pipeline {
    agent any
    stages {
        stage('Build') {// Timeout counter starts AFTER agent is allocated
            steps {
               script {
                sh "This is Build"
               }
            }
        }
        stage('Test') {
            steps {
                script {
                    sh "This is Test"
               }
            }
        }
        stage('Deploy') {
            steps {
                script {
                sh "This is Deploy"
               }
            }
        }
    }
}