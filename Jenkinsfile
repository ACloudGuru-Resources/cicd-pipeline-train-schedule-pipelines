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
                stage('db test') {
                    steps {
                        echo 'db testing'
                    }
                }
                stage ('Unit test') {
                    steps {
                        echo 'unit testing'
                    }
                }
            }
        }
        stage('Browser Test') {
            parallel {
                stage ('Chrome test') {
                    steps {
                        echo 'Chrome test'
                    }
                }
                stage ('Firefox test') {
                    steps {
                        echo 'firefox test'
                    }
                }
                stage ('Edge test') {
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
                        echo 'Staging the app'
                    }
                }
                stage('Staging 2') {
                    steps {
                        echo 'Staging the app...'
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
