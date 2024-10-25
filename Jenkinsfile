pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Running Build'  // Use standard single quotes
                sh './gradlew build --no-daemon'  // Shell command to run Gradle build
                archiveArtifacts artifacts: 'dist/trainSchedule.zip'  // Archive artifacts step
            }
        }
    }
}
