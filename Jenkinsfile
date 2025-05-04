pipeline {
    agent {
        docker {
            image 'node:lts' 
        }
    }
    stages {
        stage('Checkout Code') {
            steps {
                echo "Checking out code..."

            }
        }
        stage('Install Dependencies') {
            steps {
                echo 'Installing Node.js dependencies...'
                sh 'npm install'
            }
        }
        stage('Run Tests') {
            steps {
                echo 'Running tests...'
                sh 'npm test'
            }
        }

    }
    post {
        success {
            echo 'CI Pipeline successful! Build and tests passed.'
        }
        failure {
            echo 'CI Pipeline failed. Check console output for errors.'
        }
        always {
            echo 'Pipeline finished.'
        }
    }
}