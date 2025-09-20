pipeline {
    agent any

    tools {
        jdk 'JDK17'   // Name of JDK you configured in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Aditya1664/assignment.git', branch: 'master'
            }
        }

        stage('Build') {
            steps {
                // Create bin folder to store compiled classes
                bat 'mkdir Desktop\\bin'
                // Compile main.java
                bat 'javac -d Desktop\\bin Desktop\\src\\main.java'
            }
        }

        stage('Run') {
            steps {
                // Run the compiled Java program
                bat 'java -cp Desktop\\bin main'
            }
        }
    }
}
