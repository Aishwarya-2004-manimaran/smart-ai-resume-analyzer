pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                echo 'Cloning Repository...'
                git 'https://github.com/Aishwarya-2004-manimaran/smart-ai-resume-analyzer.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building project...'
                // Example: run a Python script or any build command
                sh 'echo No build steps defined yet'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'echo No tests defined yet'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying project...'
                sh 'echo No deploy steps defined yet'
            }
        }
    }
}
