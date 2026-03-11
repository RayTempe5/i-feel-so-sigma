pipeline {
    agent any

    environment {
        PRODUCTION_SERVER = "${env.PRODUCTION_SERVER}"
        APP_ENV = "${env.APP_ENV}"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'echo Building i-feel-so-sigma...'
            }
        }

        stage('Testing') {
            steps {
                sh 'echo Running tests...'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                    cd /home/prod/i-feel-so-sigma
                    git pull origin main
                    composer install --no-dev
                    php artisan migrate --force
                    php artisan config:cache
                    php artisan route:cache
                '''
            }
        }
    }

    post {
        success {
            echo 'Deploy Berhasil!'
        }
        failure {
            echo 'Deploy Gagal!'
        }
    }
}
