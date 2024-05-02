pipeline {
    agent any
    triggers{
        pollSCM('H/2 * * * *')
    }
    stages {
        stage('Build Application') {
            steps {
                sh 'mvn clean install'
            }  
        }
        stage('Deploy Exchange') {
            environment {
                ANYPOINT_CREDENTIALS = credentials('tonyhawkanypointtrainingcredentials')
            }
            steps {
                sh "mvn deploy"
            }
        }
    }
}