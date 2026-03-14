pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    environment {
        MAVEN_OPTS = "-Dmaven.repo.local=.m2/repository"
    }

    stages {

        stage('Build') {
            steps {
                echo "Compiling project..."
                bat 'mvn -T 1C clean compile'
            }
        }

        stage('Unit Tests') {
            steps {
                echo "Running unit tests..."
                bat 'mvn test'
            }
        }

        stage('Package') {
            steps {
                echo "Packaging application..."
                bat 'mvn package -DskipTests'
            }
        }

    }

    post {
        success {
            archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
        }
    }
}
