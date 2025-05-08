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

        stage('Deploy') {
            steps {
                echo 'Deploy stage - future Docker/EKS steps'
            }
        }
    }
}

