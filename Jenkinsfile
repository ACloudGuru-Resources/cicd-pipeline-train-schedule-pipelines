pipeline {
    agent any
    stages {
        stage ('Build') {
            steps {
                echo ('Build running')
                sh './gradlew build --no-daemon'
                archieveArtifact artifact: 'dist/trainSchedule.zip'
            }
        }
    }
}
