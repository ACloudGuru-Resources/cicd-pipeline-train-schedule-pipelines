CODE_CHANGES = getChanges()
pipeline {
  agent any
  stages {
    stage ('Build') {
      steps {
        echo 'Running build automation'
      }
    }
    stage("Test") {
      when {
        expression {
            BRANCH_NAME == 'dev' || BRANCH_NAME == 'master' || CODE_CHANGES == true
        }
      }
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
