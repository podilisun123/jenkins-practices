pipeline {
    agent { 
        label 'AGENT-1' 
    }
    options {
        timeout(time: 60, unit: 'SECONDS')
        disableConcurrentBuilds()
    }
    stages {
        stage('Build') {
            steps {
               sh 'echo this is build stage'
            }
        }
        stage('Test') {
            steps {
                sh 'echo this is test stage'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo this is deploy stage'
            }
        }
    }
}