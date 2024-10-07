pipeline {
    agent any

    parameters {
        choice(name: 'environmentname', choices: ['dev', 'test', 'prod'], description: 'Select the environment to deploy')
    }

    environment {
        ENV_NAME = "${params.environmentname}" // Use parameter value from the job configuration
    }

    stages {
        stage('Build') {
            steps {
                script {
                    // Print environment name to make sure the parameter is passed correctly
                    echo "Deploying to environment: ${ENV_NAME}"
                }
            }
        }
        // Add more stages as needed
    }
}
