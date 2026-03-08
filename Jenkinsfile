pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Compiling Java code'
                bat 'javac Hello.java'
            }
        }

        stage('Run') {
            steps {
                echo 'Running Java program'
                bat 'java Hello'
            }
        }

    }

    post {
        success {
            echo 'Pipeline executed successfully'
        }
        failure {
            echo 'Pipeline failed'
        }
    }
}
