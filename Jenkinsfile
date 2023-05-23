pipeline {
  agent any
  stages {
    stage ('Build') {
      steps {
        echo 'Running build automation'
        sh 'export JAVA_HOME=/path/to/java11'
        archiveArtifacts artifacts: 'dist/trainSchedule.zip'
        sh './gradlew build --no-daemon --debug'
        
      }
    }
  }
}
