pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo "Compiling Java file..."
                bat 'mvn compile'
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                bat 'mvn test'
            }
        }

        stage('Package') {
            steps {
                echo "Creating JAR file..."
                bat 'mvn package'
            }
        }

    }

    post {
        success {
            archiveArtifacts artifacts: 'target/*.jar'
        }
    }
}
