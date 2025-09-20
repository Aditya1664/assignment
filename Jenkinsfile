pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Aditya1664/assignment.git'
            }
        }

        stage('Compile Java') {
            steps {
                // Create bin folder
                bat 'mkdir bin'
                // Compile Java files from src to bin
                bat 'javac src\\Main.java -d bin'
            }
        }

        stage('Run Java') {
            steps {
                // Run the compiled Java program
                bat 'java -cp bin Main'
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully.'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
