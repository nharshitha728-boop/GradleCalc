pipeline {
    agent any
    
    // THIS IS THE MISSING PIECE
    tools {
        gradle 'gradle8' // This name MUST match exactly what you typed in Global Tool Configuration
        jdk 'JDK21'      // This name MUST match exactly what you typed in Global Tool Configuration
    }

    stages {
        stage('Build & Test') {
            steps {
                echo 'Running Gradle...'
                // Since we are using the Jenkins Tool, we use 'gradle' directly
                bat 'gradle clean test'
            }
        }
    }
    
    post {
        always {
            junit '**/build/test-results/test/*.xml'
        }
    }
}
