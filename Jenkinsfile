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
                        echo "building version"
                    }
                }
            }
        }
        stage('Parallel Stage 2') {
            parallel {
                stage('test') {
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
