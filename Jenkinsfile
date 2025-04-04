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
    }
}
