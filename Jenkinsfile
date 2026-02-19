pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                checkout scm
            }
        }

        stage('Build Backend Image') {
            steps {
                script {
                    docker.build("backend-image", "./backend")
                }
            }
        }

        stage('Pull NGINX Image') {
            steps {
                sh 'docker pull nginx'
            }
        }

        stage('Done') {
            steps {
                echo 'Pipeline Completed Successfully!'
            }
        }
    }
}
