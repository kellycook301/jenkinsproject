pipeline {
    agent any
    tools {
        maven 'maven_3_6_3' 
    }
    stages {
        stage("Build Stage") {
            steps {
                echo 'building the application...'
                sh 'mvn clean compile'
            }
        }
        stage("Test Stage") {
            steps {
                echo 'testing the application...'
                    sh 'mvn test'
            }
        }
        stage("Deploy Stage") {
            steps {
                echo 'deploying the application'
                    sh 'mvn deploy'
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

