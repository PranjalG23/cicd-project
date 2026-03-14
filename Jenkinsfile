pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                // Explicitly checkout main branch
                git branch: 'main', url: 'https://github.com/PranjalG23/cicd-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t cicd-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                # Stop and remove container if exists
                docker stop cicd-container || true
                docker rm cicd-container || true

                # Run new container
                docker run -d -p 3000:3000 --name cicd-container cicd-app
                '''
            }
        }

    }
}