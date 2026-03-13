pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo "Compiling Java file..."
                bat 'javac src/Hello.java -d out'
            }
        }

        stage('Test') {
            steps {
                echo "Running application..."
                bat 'java -cp out Hello'
            }
        }

        stage('Package') {
            steps {
                echo "Creating JAR file..."
                bat 'jar cf hello.jar -C out Hello.class'
            }
        }

    }

    post {
        success {
            archiveArtifacts artifacts: '*.jar'
        }
    }
}
