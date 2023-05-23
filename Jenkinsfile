CODE_CHANGES = getChanges()
pipeline {
  agent any
  enviroment {
      NEW_VERSION = '1.3.0' 
  }
  stages {
    stage ('Build') {
      steps {
        echo "building version ${NEW_VERSION}"
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
