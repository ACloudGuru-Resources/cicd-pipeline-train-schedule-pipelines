pipeline{
  agent any
  stages {
    stage ('Create Artifacts') {
      steps {
        script {
          sh "touch testfile"
          sh "git add testfile"
        }
      }
    }
    stage ('Commit changes') {
      steps {
        script {
          sh "git commit -m 'update from Jenkins Pipeline'"
        }
      }
    }
    stage ('Push to Git Repository') {
      steps {
        script {
          sh "git push -u origin HEAD:main"
        }
      }
    }
  }
}
