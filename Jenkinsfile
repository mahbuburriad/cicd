pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                sh 'composer install'
                sh 'cp .env.example .env'
                sh 'php artisan key:generate'
                sh 'php artisan storage:link'
            }
        }
        stage('Test') { 
            steps {
                sh './vendor/bin/phpunit'
            }
        }
        stage('Deploy') { 
            steps {
                echo "deploy"
            }
        }
    }
}