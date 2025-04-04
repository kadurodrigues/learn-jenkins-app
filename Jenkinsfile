pipeline {
    agent any

    environment {
        NODE_VERSION = "18.16.1"  // Adjust based on your project needs
    }

    stages {
        stage('Install Dependencies') {
            steps {
                script {
                    sh "nvm install $NODE_VERSION"
                    sh "nvm use $NODE_VERSION"
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
