pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo "Building the project..."
            }
        }
        stage('Test'){
            steps{
                echo "Running tests..."
            }
        }
        stages('Package'){
            steps{
                echo "Packaging the application..."
            }
        }
        

    }
}
