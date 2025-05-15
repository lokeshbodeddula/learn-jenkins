pipeline {
    agent {
        label 'AGENT-1'
    }
    stages {
        stage('Build') {// Timeout counter starts AFTER agent is allocated
            steps {
                sh 'echo This is Build'
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
                error 'pipeline failed'
            }
        }
    }
    post {
        always{
            echo "THis section runs always"
        }
        success{
            echo "This section run when pipeline success"
        }
        failure{
            echo "This section run when pipeline fails"
        }
    }
}