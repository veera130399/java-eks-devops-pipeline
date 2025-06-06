pipeline {
    agent any

    stages {
        stage('Build with Maven') {
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
                        def dockerImage = docker.build("veera130399/java-eks-devops-pipeline")
                        docker.withRegistry('', 'docker-hub-credentials') {
                            dockerImage.push('latest')
                        }
                    }
                }
            }
        }
    }
}

