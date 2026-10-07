pipeline {
    agent {
        label 'AGENT-1'
    } 
    options {
        timeout(time: 20, unit: 'SECONDS') 
    }
    environment {
        KEY1 = 'VALUE1'
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
        stage('print params') {
            steps {
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
                echo env
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        sucess { 
            echo 'I will  say only in sucess Hello again!'
        }
        failure {
            echo 'i wil say only in failure'
        }
    
}
