@Library('docker') _

pipeline{

    agent any 

    stages{

        stage('Git Checkout'){
           
            steps{

                script{
                 
                 git branch: 'main', url: 'https://github.com/VishalTx/innovation-task-php.git'

                }
            }
        }
        stage('Build') {
            steps {
                script {
                    // Build the Docker image using Docker Compose
                    withEnv(['PATH+DOCKER=/usr/bin']) {
                    dockerCompose(build: true, file: 'docker-compose.yml')
                    }
                }
            }
        }
    }
}