pipeline {
    agent any

    environment {
        GIT_REPO_URL = 'https://github.com/zubiks10/JenkinsNatWest.git'
        MAVEN_HOME = tool name: 'Maven', type: 'ToolLocation'  // Adjust the Maven tool location if needed
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    // Checkout the code from the specified GitHub repository
                    echo "Cloning repository from ${GIT_REPO_URL}"
                    git url: GIT_REPO_URL
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    // Build the project using Maven
                    echo 'Building the project...'
                    sh "'${MAVEN_HOME}/bin/mvn' clean install -DskipTests"
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Run tests using Maven
                    echo 'Running tests...'
                    sh "'${MAVEN_HOME}/bin/mvn' test"
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Placeholder for deployment steps
                    echo 'Deploying the project...'
                    // Add deployment commands, such as: sh './deploy.sh'
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully.'
        }
        failure {
            echo 'There was an issue with the build or deployment.'
        }
    }
}
