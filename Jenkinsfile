pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Change directory to where the Dockerfile is located
                    dir('/home/react-jenkin-docker') {
                        // Build Docker image
                        sh 'docker build -t jenkins-node-image .'
                    }
                }
            }
        }
        stage('Run') {
            steps {
                // Run Docker container
                sh 'docker run -d -p 5000:3000 jenkins-node-image'
            }
        }
        stage('Final') {
            steps {
                // List running Docker containers
                sh 'docker ps'
            }
        }
    }
}
