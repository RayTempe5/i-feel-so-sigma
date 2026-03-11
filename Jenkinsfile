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
                sh 'echo Deploy sukses ke production!'
                sh 'echo Aplikasi berhasil dideploy'
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
