pipeline {
    agent any
    stages {
        stage("Build Stage") {
            steps {
                echo 'building the application?'
            }
        }
        stage("Test Stage") {
            steps {
                echo 'testing the application!'
            }
        }
        stage("Deploy Stage") {
            steps {
                echo 'deploying the application!'
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

