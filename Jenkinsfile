pipeline {
    agent any

    tools {
        nodejs "NodeJS-18"  // Use NodeJS installed in Jenkins
    }

    stages {
        stage('Install Dependencies') {
            steps {
                script {
                    sh "npm ci"  // Ensures a clean dependency install
                }
            }
        }
        stage('Run Unit Tests') {
            steps {
                sh 'npm run test'
            }
        }
        stage('Deploy') {
            steps {
                sh "npm i netlify-cli"
                sh "node_modules/.bin/netlify --version"
            }
        }
    }
}
