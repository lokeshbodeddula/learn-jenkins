pipeline {
    agent {
        label 'AGENT-1'
    }
    options {
        timeout(time: 10, unit: 'SECONDS')
    }
    stages {
        stage('Build') {// Timeout counter starts AFTER agent is allocated
            steps {
                sh 'echo This is Build'
                sh 'sleep 10'
            }
        }
        stage('Test') {
            steps {
                    sh 'echo This is Test'
               
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo This is Deploy'
            }
        }
    }
    post {
        always{
            echo "THis section runs always"
            deleteDir() 
        }
        success{
            echo "This section run when pipeline success"
        }
        failure{
            echo "This section run when pipeline fails"
        }
    }
}