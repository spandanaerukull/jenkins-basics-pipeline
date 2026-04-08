// skeleton jenkins file for a basic pipeline with build, test, and deploy stages
pipeline{  // root element of the pipeline, defines the entire pipeline structure
    agent  {
        label 'AGENT-1' // this specifies that the pipeline should run on any available agent that has the label 'AGENT-1', this allows for flexibility in choosing where the pipeline will execute, as it can run on any node that is part of the Jenkins environment, whether it's a master or a slave node, as long as it has the specified label.
    } 
    // Build the application
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
    post { // post section defines actions to take after the pipeline execution, such as always deleting the workspace directory and printing messages based on the success or failure of the build.
        always { // this block will be executed regardless of the build result, it is useful for cleanup actions that should always be performed, such as deleting the workspace directory to ensure that any temporary files or artifacts created during the build process are removed and do not consume unnecessary disk space.
            echo "Cleaning up workspace..."
            deleteDir() // this step will delete the workspace directory after the pipeline execution, regardless of the build result, this is useful to ensure that any temporary files or artifacts created during the build process are removed and do not consume unnecessary disk space.
        }
        success {
            echo "Build succeeded!" // this step will be executed only if the build is successful, it prints a message indicating that the build succeeded.
        }
        failure {
            echo "Build failed!" // this step will be executed only if the build fails, it prints a message indicating that the build failed.
        }
    }
    





}


