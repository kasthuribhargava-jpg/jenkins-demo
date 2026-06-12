pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Code pulled from GitHub successfully'
            }
        }

        stage('Build') {
            steps {
                sh '''
                echo "===== BUILD STAGE ====="
                pwd
                ls -la
                '''
            }
        }

        stage('Test') {
            steps {
                sh '''
                echo "===== TEST STAGE ====="
                echo "Running application tests..."
                '''
            }
        }

        stage('Package') {
            steps {
                sh '''
                echo "===== PACKAGE STAGE ====="
                mkdir -p artifact
                echo "Build Successful" > artifact/build.txt
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                echo "===== DEPLOY STAGE ====="
                echo "Application deployed successfully"
                '''
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: 'artifact/*'
            echo 'Pipeline completed successfully'
        }

        failure {
            echo 'Pipeline failed'
        }

        always {
            echo 'Pipeline execution finished'
        }
    }
}