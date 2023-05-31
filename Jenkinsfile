pipeline {
    agent any
    parameters {
        // Define a parameter for the version to deploy on prod
        choice(name: 'VERSION', choices: ['1.1.0', '1.1.1', '1.1.2'], description: 'Which version do you want to deploy on production?')
        // Define a parameter to determine whether to execute tests or not
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Execute tests')
    }
    environment {
        // Set a custom environmental variable
        NEW_VERSION = '1.3.0'
    }
    stages {
        stage('Parallel Stage 1') {
            parallel {
                stage('init') {
                    steps {
                        script {
                            gv = load "script.groovy"
                        }
                    }
                }
                stage('build') {
                    when {
                        // Execute this stage only if the executeTests parameter is true
                        expression {
                            params.executeTests
                        }
                    }
                    steps {
                        script {
                            gv.buildApp()
                        }
                        // Access the value of the environmental variable without using double quotes
                        echo "building version ${NEW_VERSION}"
                    }
                }
            }
        }
        stage('Parallel Stage 2') {
            parallel {
                stage('test') {
                    when {
                        // Execute this stage only if the branch name is 'dev' or 'master'
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
                        echo "deploying version ${params.VERSION}"
                    }
                }
            }
        }
    }
}
