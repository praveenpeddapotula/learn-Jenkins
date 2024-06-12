pipeline {
    agent {
        label 'AGENT-1'
    }
    options {
        timeout (time: 10, unit: 'MINUTES')
    }
    stages {
        stage('Build') {
            steps {
               sh 'echo this is build stage'
            }
        }
        stage('Test') {
            steps {
                sh ' echo this is test stage'
                sh ' sleep 10'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo this is deploy stage'
            }
        }
    }
}