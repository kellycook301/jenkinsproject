pipeline {
    agent any
    // environment {
    //     NEW_VERSION = '1.3.0'
    //     SERVER_CREDENTIALS = credentials('server-credentials')
    // }
    stages {
        stage("Build Stage") {
            steps {
                echo 'building the application...'
                withMaven(maven : 'maven_3_6_3') {
                    sh 'mvn clean compile'
                }
            }
        }
        stage("Test Stage") {
            steps {
                echo 'testing the application...'
                withMaven(maven : 'maven_3_6_3') {
                    sh 'mvn test'
                }
            }
        }
        stage("Deploy Stage") {
            steps {
                echo 'deploying the application'
                withMaven(maven : 'maven_3_6_3') {
                    sh 'mvn deploy'
                }
            }
        }
    }

    post {
        always {
            // will be executed no matter if the build fails or succeeds
            echo 'this will always execute no matter what'
        }
        success {
            // only executes if the build succeeds
            echo 'build succeeded'
        }
        failure {
            // only executes if the build fails
            echo 'build failed'
        }
    }
}

