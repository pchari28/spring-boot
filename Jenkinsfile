pipeline {
    agent any
    environment {
        name = 'Pritesh'
    }
    parameters {
        string(name: 'person', defaultValue: 'Pritesh Chari')
        booleanParam(name: 'isMale', defaultValue: 'true')
        choice(name: 'Department', choices: ['Prod','Dev','Staging'])
    }
    stages {
        stage('Run a command') {
            steps {
                sh 'date'
                sh 'pwd'
            }
        }
        stage('Environment variable') {
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${person}"'
                sh 'echo "${Department}"'
            }
        }
        stage('Parameters') {
            steps {
                echo 'Deploy on test'
            }
        }
        stage('Continue to Prod ?') {
            input {
                message "Should we proceed"
                ok "Yes we should"
            }
            steps {
                echo 'Deploy on prod'
            }
        }
    }
}
