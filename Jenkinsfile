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
        stage('Test') {
            parallel {
                stage('init') {
                    steps {
                        script {
                            gv = load "script.groovy"
                        }
                    }
                }
                stage('dbtest') {
                    steps {
                        echo 'db testing'
                    }
                }
                stage ('unittest') {
                    steps {
                        echo 'unit testing'
                    }
                }
            }
        }
        stage('BrowseTest') {
            parallel {
                stage ('chrome test') {
                    steps {
                        echo 'Chrome test'
                    }
                }
                stage ('firefox test') {
                    steps {
                        echo 'firefox test'
                    }
                }
                stage ('edge test') {
                    steps {
                        echo 'edge test'
                    }
                }
            }
        }
        stage('Staging') {
            parallel {
                stage('Staging 1') {
                    steps {
                        echo 'testing the app'
                    }
                }
                stage('staging 2') {
                    steps {
                        echo 'deploying the app'
                    }
                }
            }
        }
        stage('Production') {
            steps {
                echo "Deploying the application... with ${NEW_VERSION}"
            }
        }
    }
}
