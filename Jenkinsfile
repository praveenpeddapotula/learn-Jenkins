pipeline {
    agent {
        label 'AGENT-1'
    }
    options {
        timeout (time: 10, unit: 'MINUTES')
        disableConcurrentBuilds()
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
        stage("print params"){
            steps{
                echo "Hello ${params.PERSON}"
                echo "Biography: ${params.BIOGRAPHY}"
                echo "TOGGLE: ${params.TOGGLE}"
                echo "choice is ${params.CHOICE}"
            }
        }
        post{
            always{
                echo " i will say hello again "
            }
            success { 
                echo " i will run when pipeline is success"

            }
            failure{
                echo " i will run when pipeline is failure"
            }
        }
    }
}