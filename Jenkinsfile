pipeline {
    agent any

    tools {
        gradle 'gradle8' 
        jdk 'JDK17' 
    }

    stages {
        stage('Build & Test') {
            steps {
                // We keep everything in one stage for simplicity while debugging
                echo 'Running Gradle Build and Test...'
                bat 'gradle clean test'
            }
        }
    }

    post {
        always {
            // This now stays inside the agent scope correctly
            script {
                echo 'Recording Test Results...'
                junit '**/build/test-results/test/*.xml'
            }
        }
    }
}
