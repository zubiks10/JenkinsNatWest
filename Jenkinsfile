pipeline {
    agent any  // Run on any available agent

    environment {
        // Define any environment variables here
        // e.g., PATH = '/usr/local/bin:$PATH'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the repository
                git https://github.com/zubiks10/JenkinsNatWest.git
            }
        }

        stage('Build') {
            steps {
                // Example build step: Compile or build your project
                script {
                    echo 'Building the project...'
                    // Add build commands here, like:
                    // sh './build.sh'
                }
            }
        }

        stage('Test') {
            steps {
                // Example test step: Run tests on the project
                script {
                    echo 'Running tests...'
                    // Add test commands here, like:
                    // sh './run_tests.sh'
                }
            }
        }

        stage('Deploy') {
            steps {
                // Example deploy step: Deploy the application
                script {
                    echo 'Deploying the application...'
                    // Add deploy commands here, like:
                    // sh './deploy.sh'
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
