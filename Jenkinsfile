pipeline {
    agent any
    environment {
        NEW_VERSION = '1.3.0'
        SERVER_CREDENTIALS = credentials('server-credentials')
    }
    stages {
        stage("build") {
            steps {
                echo 'building the application...'
            }
        }
        stage("test") {
            steps {
                echo 'testing the application...'
                echo "building version ${NEW_VERSION}"
            }
        }
        stage("deploy") {
            steps {
                echo 'deploying the application'
                echo "deploying with ${SERVER_CREDENTIALS}"
                sh "${SERVER_CREDENTIALS}"
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

