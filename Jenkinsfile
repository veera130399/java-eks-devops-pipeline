pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Docker Build') {
            steps {
                echo 'Docker build and push steps will be added here soon'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy stage - future Docker/EKS steps'
            }
        }
    }
}

