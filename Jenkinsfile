stage('Docker Build & Push') {
    steps {
        dir('java-app') {
            script {
                sh 'docker build -t veera130399/java-eks-devops-pipeline:latest .'

                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub',
                    usernameVariable: 'DOCKER_USER',
                    passwordVariable: 'DOCKER_PASS'
                )]) {
                    sh 'echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin'
                    sh 'docker push veera130399/java-eks-devops-pipeline:latest'
                }
            }
        }
    }
}

