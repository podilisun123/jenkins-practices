pipeline {
    agent { 
        label 'AGENT-1' 
    }
    options {
        timeout(time: 60, unit: 'SECONDS')
        disableConcurrentBuilds()
    }
    triggers {
        cron('* * * * *')
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    environment { 
        Greetings = 'Hello!.. Good morning'
    }
    stages {
        stage('Build') {
            steps {
               sh 'echo this is build stage'
               sh 'printenv' 
            }
        }
        stage('Test') {
            steps {
                sh 'echo this is test stage'
                echo "Hello ${params.PERSON}"
                echo "Biography: ${params.BIOGRAPHY}"
                echo "Toggle: ${params.TOGGLE}"
                echo "Choice: ${params.CHOICE}"
                echo "Password: ${params.PASSWORD}"
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo this is deploy stage'
                sh 'echo deploy test with webhook'
            }
        }
    }
    post { 
        always { 
            echo 'I will always execute'
        }
        success { 
            echo 'I will execute with success'
        }
        failure { 
            echo 'I will  say Hello with failure!'
        }
    }
}