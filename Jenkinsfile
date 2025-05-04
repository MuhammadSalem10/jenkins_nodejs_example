pipeline {
    agent {
        docker {
            image 'node:12'

            args '-v /var/run/docker.sock:/var/run/docker.sock --group-add 999'
            customWorkspace '.'
        }
    }
    stages {
        stage('Checkout Code') {
            steps {
                echo "Workspace is: ${pwd()}" 
            }
        }
        stage('Install Dependencies') {
            steps {
                echo 'Installing Node.js dependencies...'
                
                sh 'ls -la'       
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
      always {
          echo 'Pipeline finished.'
      }
      success {
          echo 'CI Pipeline successful! Build and tests passed.'
      }
      failure {
          echo 'CI Pipeline failed. Check console output for errors.'
      }
    }
}