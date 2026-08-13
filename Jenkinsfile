pipeline {
    agent { 
        label 'AGENT-1' 
    }
    options {
        timeout(time: 60, unit: 'SECONDS')
        disableConcurrentBuilds()
    }
    environment { 
        Greetings = 'Hello!.. Good morning'
    }
    stages {
        stage('Build') {
            steps {
               sh 'echo this is build stage'
               env 
            }
        }
        stage('Test') {
            steps {
                sh 'echo this is test stage'
                sleep 10
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo this is deploy stage'
            }
        }
    }
}