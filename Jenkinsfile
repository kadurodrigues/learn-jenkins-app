pipeline {
    agent any

    stages {
        stage('Without Docker') {
            steps {
                sh 'echo without docker'
            }
        }
        stage('With Docker') {
            agent {
                docker {
                    image 'node:18-alpine'
                }
            }
            steps {
                sh 'echo with docker'
                sh 'npm --version'
            }
        }
    }
}
