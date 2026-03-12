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
                sshagent(credentials: ['ssh-prod']) {
                    sh 'ssh -o StrictHostKeyChecking=no ray@172.23.134.44 "echo SSH Jenkins berhasil!"'
                }
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
