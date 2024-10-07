pipeline {
    agent any

    // Define parameters
    parameters {
        string(name: 'environmentname', defaultValue: 'prod', description: 'Environment to deploy to')
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the repository
                checkout scm
                script {
                        echo "Deploying to environment provility: ${env.GIT_BRANCH}"
                                }
            }

        }

        stage('Set Environment') {
            steps {
                script {
                    // Set environment based on the branch
                    if (env.GIT_BRANCH == 'origin/main') {
                        env.environmentname = 'dev'
                    } else {
                        env.environmentname = 'prod'
                    }
                    echo "Deploying to environment: ${env.GIT_BRANCH}"
                }
            }
        }

        stage('Build') {
            steps {
                // Add your build steps here
                echo "Building the project for ${env.environmentname}..."
                // Example: sh './build.sh' (replace with your build command)
            }
        }

        stage('Deploy') {
            steps {
                // Add your deployment steps here
                echo "Deploying to ${env.environmentname} environment..."
                // Example: sh './deploy.sh' (replace with your deployment command)
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}
