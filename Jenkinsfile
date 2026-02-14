pipeline {
    agent any
    
    stages {
        stage('Build & Test') {
            steps {
                // 'clean test' deletes old files and runs JUnit
                bat 'gradlew clean test'
            }
        }
    }
    
    post {
        always {
            // Gradle puts test results here by default
            junit 'build/test-results/test/*.xml'
        }
    }
}
