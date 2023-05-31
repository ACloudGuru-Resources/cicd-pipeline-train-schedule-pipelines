pipeline {
    agent any

    stages {
        stage('Parallel Stage') {
            parallel {
                stage('Stage 1') {
                    steps {
                        echo 'Running Stage 1'
                        // Add your build steps for Stage 1 here
                    }
                }
                stage('Stage 2') {
                    steps {
                        echo 'Running Stage 2'
                        // Add your build steps for Stage 2 here
                    }
                }
                stage('Stage 3') {
                    steps {
                        echo 'Running Stage 3'
                        // Add your build steps for Stage 3 here
                    }
                }
            }
        }
    }
}
