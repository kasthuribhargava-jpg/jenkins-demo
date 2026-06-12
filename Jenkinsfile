pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Code pulled from GitHub'
            }
        }

        stage('Build') {
            steps {
                sh 'ls -la'
            }
        }

        stage('Test') {
            steps {
                sh 'echo Running Tests'
            }
        }

        stage('Package') {
            steps {
                sh '''
                mkdir -p artifact
                echo Build Successful > artifact/build.txt
                '''
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: 'artifact/*'
        }
    }
}