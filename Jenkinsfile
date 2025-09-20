pipeline {
    agent any

    environment {
        IMAGE_NAME = "aditya1664/mynodeapp"
        IMAGE_TAG = "1.0"
    }

    stages {

        stage('Build Docker Image') {
            steps {
                bat "docker build -t %IMAGE_NAME%:%IMAGE_TAG% ."
            }
        }

        stage('Run Docker Container') {
            steps {
                bat "docker stop nodeapp || exit 0"
                bat "docker rm nodeapp || exit 0"
                bat "docker run -d -p 9090:8080 --name nodeapp %IMAGE_NAME%:%IMAGE_TAG%"
            }
        }
    }

    post {
        success {
            echo "Pipeline finished successfully. App running on port 9090."
        }
        failure {
            echo "Pipeline failed!"
        }
    }
}
