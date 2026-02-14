pipeline {
    agent any
    
    tools {
        gradle 'gradle8' 
        jdk 'JDK17'      // Changed from JDK21 to JDK17 to match your Jenkins
    }

    stages {
        stage('Build & Test') {
            steps {
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
