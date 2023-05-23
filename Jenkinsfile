pipeline {
  agent any
  stages {
    stage ('Build') {
      steps {
        echo 'Running build automation'
        sh './gradlew build --no-daemon --info'
        archiveArtifacts artifacts: 'dist/trainSchedule.zip'
      }
    }
  }
}
