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
                    script {
                        dockerImage = docker.build("veera130399/devops-java-app")
                        docker.withRegistry('', 'docker-hub-credentials') {
                            dockerImage.push()
                        }
                    }
                }
            }
        }
    }
}

