pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                echo 'Cloning Repository...'
                git branch: 'main', url: 'https://github.com/Aishwarya-2004-manimaran/smart-ai-resume-analyzer.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
            }
        }
    }
}
