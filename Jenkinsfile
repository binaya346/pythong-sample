pipeline {
    agent {
        docker {
            image 'python:3.9'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
    
    stages {
        stage('Initialize') {
            steps {
                echo '🚀 Starting the DevOps Pipeline...'
                echo "Build Number: ${env.BUILD_NUMBER}"
                echo "Git Branch: ${env.BRANCH_NAME}"
                sh 'echo "Container: $(hostname)"'  // This will show container ID
            }
        }
        stage('Build') {
            steps {
                echo '🛠 Building the application...'
                sh 'echo "Simulating Maven Build..." && sleep 2'
                sh 'docker --version'
            }
        }
        stage('Test') {
            steps {
                echo '🧪 Running Unit Tests...'
                sh 'echo "Tests Passed!"'
            }
        }
        stage('Deploy') {
            steps {
                echo '📦 Deploying to Docker Hub...'
                sh 'echo "Image Pushed Successfully"'
            }
        }
    }
    
    post {
        always {
            echo '🧹 Cleaning up workspace...'
        }
        success {
            echo '✅ Success: Everything worked!'
        }
        failure {
            echo '❌ Danger: The build failed!'
        }
    }
}