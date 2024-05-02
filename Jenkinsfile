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
                ANYPOINT_CREDENTIALS = credentials('5582a536-8144-4165-a4fa-3e47aeadf224')
            }
            steps {
                sh "mvn deploy"
            }
        }
    }
}