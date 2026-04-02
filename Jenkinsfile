// skeleton jenkins file for a basic pipeline with build, test, and deploy stages
pipeline{  // root element of the pipeline, defines the entire pipeline structure
    agent any  // 

    stages {
        stage('Build') {
            steps {
                echo "Building the application..."
                sh 'echo "Building..."' 
            }
        }
        stage('Test') {
            steps {
                echo "Running tests..."
                sh 'echo "Testing..."'
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying the application..."
                sh 'echo "Deploying..."'
            }
        }
    }

}