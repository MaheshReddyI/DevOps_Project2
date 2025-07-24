pipeline {
    agent any

    environment {
        IMAGE_NAME = "devops_project2"
    }

    stages {
        stage('Clone') {
            steps {
                git url: 'https://github.com/MaheshReddyI/DevOps_Project2.git', branch: 'main'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t $IMAGE_NAME .'
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    sh 'docker run -d -p 8081:80 --name ${IMAGE_NAME}_container $IMAGE_NAME'
                }
            }
        }
    }

    post {
        always {
            echo "Pipeline completed"
        }
    }
}

