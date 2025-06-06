stage('Docker Build & Push') {
    steps {
        dir('java-app') {
            script {
                dockerImage = docker.build("veera130399/java-eks-devops-pipeline")
                docker.withRegistry('', 'docker-hub-credentials') {
                    dockerImage.push('latest')
                }
            }
        }
    }
}

