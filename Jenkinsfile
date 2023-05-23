pipeline {
  agent any
  stages {
    stage ('Build') {
      steps {
        echo 'Running build automation'
        sh 'export JAVA_HOME=/path/to/java11'
      }
    }
    stage("Test") {
      steps {
        echo 'Testing the application'
      }
    }
    stage("Deploy") {
      steps {
        echo 'Deploying the application'
      }
    }
  }
}

