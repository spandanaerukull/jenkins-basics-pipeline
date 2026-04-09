// skeleton jenkins file for a basic pipeline with build, test, and deploy stages
pipeline{  // root element of the pipeline, defines the entire pipeline structure
    agent  {
        label 'AGENT-1' // this specifies that the pipeline should run on any available agent that has the label 'AGENT-1', this allows for flexibility in choosing where the pipeline will execute, as it can run on any node that is part of the Jenkins environment, whether it's a master or a slave node, as long as it has the specified label.
    } 
    environment { // use this section to define environment variables that can be used throughout the pipeline, this is useful for storing values that are commonly used in multiple stages or steps, such as the name of the course or the version of the application being built.
        COURSE = 'jenkins' // Define environment variables for the pipeline, in this case we are defining a variable named COURSE with the value 'jenkins', this variable can be accessed and used throughout the pipeline execution, for example in shell commands or in other stages, it allows for better maintainability and readability of the pipeline by centralizing the definition of commonly used values.
    }

    options { // Define options for the pipeline, these options include setting a timeout for the pipeline execution to prevent it from running indefinitely and disabling concurrent builds to ensure that only one instance of the pipeline runs at a time, which can help avoid conflicts and resource contention.
        timeout(time: 30, unit: 'MINUTES')  // this option sets a timeout for the pipeline execution, if the pipeline takes longer than the specified time (30 minutes in this case), it will be automatically aborted to prevent it from running indefinitely and consuming resources unnecessarily.
        disableConcurrentBuilds() // this option disables concurrent builds, ensuring that only one instance of the pipeline runs at a time, which can help avoid conflicts and resource contention.
    }
      parameters { // Define parameters for user input when triggering the pipeline, these parameters allow users to provide input values that can be used in the pipeline execution, such as specifying a person's name, providing a biography, toggling a boolean value, making a choice from a list of options, or entering a password. These parameters can be accessed in the pipeline using the `params` object, for example `params.PERSON` to get the value of the PERSON parameter.
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password') 
    }

    // Build the application
    stages {
        stage('Build') {
            steps {
                script{ // Define the steps to execute in the Build stage, in this case we are using a script block to execute some shell commands, we are printing a message to indicate that we are building, then we are sleeping for 10 seconds to simulate a build process, after that we are printing the environment variables using the env command and finally we are printing a personalized message using the input parameter PERSON.
                           // the script block allows us to write arbitrary Groovy code, which can be useful for more complex logic or when we want to use variables and control structures that are not available in the declarative syntax. In this case, we are using it to execute a series of shell commands that simulate a build process and print some information about the environment and the input parameters.
                    sh """  
                        echo "Hello Build" 
                        env 
                        echo "Hello ${params.PERSON}"
                    """
                }
                
            }
        }
        stage('Test') {
            steps {
                script{ // Define the steps to execute in the Test stage, in this case we are using a script block to execute some shell commands, we are printing a message to indicate that we are running tests, then we are sleeping for 5 seconds to simulate a test process, after that we are printing the environment variables using the env command and finally we are printing a personalized message using the input parameter PERSON.
                echo "Running tests..."
                  sh 'echo "Testing..."'
                }
                
            }
        }
        stage('Deploy') {
            input { // Define an input step that prompts the user for confirmation before proceeding with the deployment, this is useful to ensure that the deployment is intentional and to allow for any necessary checks or approvals before deploying to production. The input step includes a message asking if we should continue, an OK button with a custom label, and specifies that only certain users (alice and bob) are allowed to submit the input. Additionally, it defines a parameter for user input, allowing the user to specify a person's name that will be used in the deployment steps.
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
            steps {
                script{
                    echo "Hello, ${params.PERSON}, nice to meet you."
                echo "Deploying the application..."
                sh 'echo "Deploying..."'
                }
                
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
            // here we can write the code to send a notification to the team about the failure, for example using email or a messaging platform like Slack, this can help ensure that the team is aware of the failure and can take appropriate action to investigate and resolve the issue.
        }

    }
    
    





}

// delete dir is used to delete the data after the pipeline execution no matter if the build is successful or not, this is used to clean up the space and when we run the next time same pipeline it will be a clean slate, this is useful to avoid any issues that may arise from leftover files or artifacts from previous builds, it ensures that each build starts with a clean workspace and can help prevent conflicts or errors caused by leftover data.
// explained the max jenkins pipeline 