pipeline {
    agent any

    environment {
        NODE_VERSION = "18.16.1"  // Adjust based on your project needs
    }

    tools {
        nodejs "NodeJS-${NODE_VERSION}"  // Use NodeJS installed in Jenkins
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
