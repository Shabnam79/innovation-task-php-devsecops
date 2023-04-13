pipeline {
    agent any 
    stages {
        stage('Git Checkout') {
            steps {
                script {
                    git branch: 'main', url: 'https://github.com/Shabnam79/innovation-task-php-devsecops'
                }
            }
        }
       stage('PHPCS') {
            steps {
                catchError(buildResult: 'Success', stageResult: 'Success') {
                sh 'phpcs ${WORKSPACE} --generator=HTML > report.html'
             }
            }
            }
        stage('Build') {
            steps {
                sh "docker-compose up -d --build"
            }
          }
        }   
}





