pipeline {
    agent any

    stages {
        stage('Who Am I') {
            steps {
                sh 'whoami'
                sh 'id'
                sh 'docker --version'
                sh 'docker ps'
            }
        }
    }
}