pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "deepochhane/node-app"
        DOCKERHUB_CREDENTIALS = 'docker-hub-creds'   // The ID you created in Jenkins
    }

    stages {
        stage('Checkout Code') {
            steps {
                git credentialsId: 'github-pat', url: 'https://github.com/DeepOchhane/node-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh "docker build -t $DOCKER_IMAGE ."
                }
            }
        }

        stage('Push Docker Image to DockerHub') {
            steps {
                withCredentials([usernamePassword(credentialsId: "$DOCKERHUB_CREDENTIALS", passwordVariable: 'DOCKER_PASSWORD', usernameVariable: 'DOCKER_USERNAME')]) {
                    sh """
                        echo "$DOCKER_PASSWORD" | docker login -u "$DOCKER_USERNAME" --password-stdin
                        docker push $DOCKER_IMAGE
                    """
                }
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                script {
                    sh "kubectl set image deployment/node-app node-container=$DOCKER_IMAGE --record"
                }
            }
        }
    }
}
