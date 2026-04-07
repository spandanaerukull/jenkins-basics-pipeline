// skeleton jenkins file for a basic pipeline with build, test, and deploy stages
pipeline{  // root element of the pipeline, defines the entire pipeline structure
    agent  {
        label 'AGENT-1' // this specifies that the pipeline should run on any available agent that has the label 'AGENT-1', this allows for flexibility in choosing where the pipeline will execute, as it can run on any node that is part of the Jenkins environment, whether it's a master or a slave node, as long as it has the specified label.
    } 
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

