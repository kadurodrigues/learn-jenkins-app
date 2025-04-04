pipeline {
    agent any

    tools {
        nodejs "NodeJS-18"  // Use NodeJS installed in Jenkins
    }

    environment {
      NETLIFY_SITE_ID = '969c63f8-477b-47d4-8c34-c78a7ba3614d'
      NETLIFY_AUTH_TOKEN = credentials('netlify-token')
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
                sh "echo deploying to prod: Site ID: $NETLIFY_SITE_ID"
                sh "node_modules/.bin/netlify status"
            }
        }
    }
}
