pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo "Building project with Maven..."
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
                echo "Packaging application..."
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
