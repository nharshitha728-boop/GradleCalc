pipeline {
    agent any

    tools {
        gradle 'gradle8.10.2' 
        jdk 'JDK17' 
    }

    stages {
        stage('Build & Test') {
            steps {
                echo 'Running Gradle...'
                // Running the build and test in one command
                bat 'gradle clean test'
            }
        }
    }

    post {
        always {
            // We use 'node' to provide the necessary FilePath context
            node('built-in' || 'master') {
                echo 'Recording Test Results...'
                junit '**/build/test-results/test/*.xml'
            }
        }
    }
}
