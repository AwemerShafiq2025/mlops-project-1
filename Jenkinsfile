pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/AwemerShafiq2025/mlops-project-1.git'
            }
        }
        stage('Build Image') {
            steps {
                sh 'docker build -t mlops-app .'
            }
        }
        stage('Push to DockerHub') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'docker-hub-creds', passwordVariable: 'DOCKER_PASSWORD', usernameVariable: 'DOCKER_USERNAME')]) {
                    sh "echo \$DOCKER_PASSWORD | docker login -u \$DOCKER_USERNAME --password-stdin"
                    sh "docker tag mlops-app \$DOCKER_USERNAME/mlops-app:latest"
                    sh "docker push \$DOCKER_USERNAME/mlops-app:latest"
                }
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker rm -f my-running-app || true'
                sh 'docker run -d --name my-running-app -p 80:80 nginx'
            }
        }
    }
}
