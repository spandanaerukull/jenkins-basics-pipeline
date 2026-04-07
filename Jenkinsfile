// skeleton jenkins file for a basic pipeline with build, test, and deploy stages
pipeline{  // root element of the pipeline, defines the entire pipeline structure
    agent any  //  specifies that the pipeline can run on any available agent, this allows for flexibility in choosing where the pipeline will execute, it can run on any node that is part of the Jenkins environment, whether it's a master or a slave node, and it will automatically select an available agent to run the pipeline.

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