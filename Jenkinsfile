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
        withCredentials([gitUsernamePassword(credentialsId: 'github_key_o9yj', gitToolName: 'Default')]) {
          sh "git push origin HEAD:main"
        }
      }
    }
  }
}
