pipeline {
    agent any

    tools {
        // Ensure this matches the EXACT name in Manage Jenkins -> Tools
        gradle 'gradle8.9' 
        jdk 'JDK17' 
    }

    stages {
        stage('Build & Test') {
            steps {
                echo 'Running Gradle Build and Test...'
                bat 'gradle clean test'
            }
        }
    }

    post {
        always {
            // No 'node' wrapper needed here!
            echo 'Recording Test Results...'
            junit '**/build/test-results/test/*.xml'
        }
    }
}
