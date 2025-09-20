pipeline {
    agent any

    environment {
        JAVA_HOME = "C:\Program Files\Java\jdk-17" // Your JDK path
        PATH = "${env.JAVA_HOME}\\bin;${env.PATH}"
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Aditya1664/assignment.git'
            }
        }

        stage('Compile') {
            steps {
                bat 'javac src\\*.java -d bin'
            }
        }

        stage('Run') {
            steps {
                bat 'java -cp bin Main'
            }
        }
    }

    post {
        success {
            echo 'Java application executed successfully.'
        }
        failure {
            echo 'Build or run failed!'
        }
    }
}
