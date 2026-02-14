pipeline {
    agent any
    stages {
        stage('Initialize Gradle') {
            steps {
                // This creates the wrapper if it's missing
                bat 'gradle wrapper' 
            }
        }
        stage('Build and Test') {
            steps {
                // This is the "Terminal Command" run by the cloud
                bat 'gradlew test'
            }
        }
    }
}
