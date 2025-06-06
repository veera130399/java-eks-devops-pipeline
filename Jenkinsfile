pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                dir('java-app') {
                    sh 'mvn clean install'
                }
            }
        }

        stage('Docker Build & Push') {
            steps {
                dir('java-app') {
                    sh 'docker build -t veera130399/java-eks-devops-pipeline:latest .'
                    // Optional: if you have Docker Hub credentials set
                    // with ID 'dockerhub'
                    withCredentials([usernamePassword(credentialsId: 'dockerhub', usernameVariable: 'DOCKER_USER', passwordVariable: 'DOCKER_PASS')]) {
                        sh 'echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin'
                        sh 'docker push veera130399/java-eks-devops-pipeline:latest'
                    }
                }
            }
        }
    }
}

