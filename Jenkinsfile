pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo "Compiling Java file..."
                bat 'javac Hello.java'
            }
        }

        stage('Test') {
            steps {
                echo "Running application..."
                bat 'java Hello'
            }
        }

        stage('Package') {
            steps {
                echo "Creating JAR file..."
                bat 'jar cf hello.jar Hello.class'
            }
        }

    }

    post {
        success {
            archiveArtifacts artifacts: '*.jar'
        }
    }
}
