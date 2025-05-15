pipeline {
    agent {
        label 'AGENT-1'
    }
    options {
        timeout(time: 10, unit: 'SECONDS')
        disableConcurrentBuilds() 
    }
    parameters { 
        string (name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?') 
        text (name: 'MESSAGE', defaultValue: 'Hello', description: 'What should I say?')
        booleanparam(name: 'TEST', defaultValue: true, description: 'This is a test')
        choice(name: 'CHOICE', choices: ['Choice 1', 'Choice 2', 'Choice 3'], description: 'This is a choice parameter')
        password(name: 'PASSWORD', defaultValue: 'password', description: 'This is a password') 
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
        stage('print params') {
            steps {
                echo "Hello ${params.PERSON}"
                echo "Biography: ${params.MESSAGE}"
                echo "Toggle: ${params.TEST}"
                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}" 
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