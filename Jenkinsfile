
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
                sh 'echo PHP test skipped'
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo Deploy ke server $PRODUCTION_SERVER'
                sh 'echo Environment: $APP_ENV'
            }
        }
    }

    post {
        success {
            echo 'Pipeline Berhasil!'
        }
        failure {
            echo 'Pipeline Gagal!'
        }
    }
}
