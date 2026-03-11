pipeline {
    agent any

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
                sh 'php artisan test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy selesai!'
            }
        }
    }

    post {
        success {
            echo 'Pipeline Berhasil!'
        }
        failure {
            echo 'Pipeline Gagal! Cek Console Output.'
        }
    }
}
