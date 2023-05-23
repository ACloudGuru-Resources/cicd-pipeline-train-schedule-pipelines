pipeline {
  agent any
  stages {
    stage ('Build') {
      steps {
        echo 'Running build automation'
        sh 'export JAVA_HOME=/path/to/java11'
        sh './gradlew build --no-daemon --debug'
        archiveArtifacts artifacts: 'dist/trainSchedule.zip'
      }
    }
  }
}
