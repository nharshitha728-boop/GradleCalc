pipeline {
    agent any

    tools {
        // Changed from 'gradle8' to 'gradle8.5' to match your Jenkins settings
        gradle 'gradle8.5' 
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
            script {
                echo 'Recording Test Results...'
                junit '**/build/test-results/test/*.xml'
            }
        }
    }
}
