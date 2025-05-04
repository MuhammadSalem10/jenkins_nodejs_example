pipeline {
    agent {
        docker {
            image 'node:12'
            args '-v /var/run/docker.sock:/var/run/docker.sock --group-add 999'
            workingDir '/var/jenkins_home/workspace/NodejsExampleCIPipeline'
        }
    }
    stages {
        stage('Checkout Code') {
            steps {
                echo 'Checking out code...'
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
}