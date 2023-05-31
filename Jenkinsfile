pipeline {
    agent any

    stages {
        stage('Parallel Stage') {
            parallel {
                stage('init') {
                    steps {
                        echo "building version  init"

                    }
                }

                stage('build') {
                    steps {
                        echo "building version ${NEW_VERSION}"
                    }
                }

                stage('test') {
                    when {
                        expression {
                            BRANCH_NAME == 'master' || BRANCH_NAME == 'dev'
                        }
                    }
                    steps {
                        echo 'testing the app'
                    }
                }

                stage('deploy') {
                    steps {
                        echo 'deploying the app'
                    }
                }
            }
        }
    }
}
