pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "resume-analyzer-image"
        DOCKER_CONTAINER = "resume-analyzer-container"
        PORT = "8501"
    }

    stages {
        stage('Clone Repository') {
            steps {
                echo '=== Cloning Repository ==='
                // ✅ Updated GitHub repo URL
                git branch: 'main', url: 'https://github.com/Aishwarya-2004-manimaran/smart-ai-resume-analyzer.git'
            }
        }

        stage('Remove Old Container and Image') {
            steps {
                echo '=== Stopping and Removing Old Container ==='
                script {
                    def stopStatus = bat(script: "docker stop %DOCKER_CONTAINER%", returnStatus: true)
                    if (stopStatus != 0) {
                        echo "Container not running"
                    }

                    def rmStatus = bat(script: "docker rm %DOCKER_CONTAINER%", returnStatus: true)
                    if (rmStatus != 0) {
                        echo "Container not found"
                    }

                    def rmiStatus = bat(script: "docker rmi %DOCKER_IMAGE%", returnStatus: true)
                    if (rmiStatus != 0) {
                        echo "Image not found or in use"
                    }
                }
            }
        }

        stage('Build Docker Image') {
            steps {
                echo '=== Building New Docker Image ==='
                bat "docker build -t %DOCKER_IMAGE% ."
            }
        }

        stage('Run Docker Container') {
            steps {
                echo '=== Running New Container ==='
                bat "docker run -d -p %PORT%:8501 --name %DOCKER_CONTAINER% %DOCKER_IMAGE%"
            }
        }
    }
}
