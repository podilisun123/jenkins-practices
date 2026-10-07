pipeline {
    agent {
        label 'AGENT-1'
    } 
    options {
        timeout(time: 20, unit: 'SECONDS') 
    }
    stages {
        stage('Build') { 
            steps {
                sh 'echo this is build' 
            }
        }
        stage('Test') { 
            steps {
               sh 'echo this is test'
               //sleep(10) 
            }
        }
        stage('Deploy') { 
            steps {
               sh 'echo this is deploy' 
            }
        }
    }
}
