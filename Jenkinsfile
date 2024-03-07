pipeline{
  agent any
  stages {
    stage ('Commit changes') {
      steps {
        script {
          sh "git commit -m 'update dbt schema'"
        }
      }
    }
    stage ('Push to Git Repository') {
      steps {
        script {
          sh "git push origin main"
        }
      }
    }
  }
}
