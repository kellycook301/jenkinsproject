CODE_CHANGES = getGitChanges()

pipeline {
    agent any

    stages {
        stage("build") {
            when {
                expression {
                    // will only build if there are code changes on 'master'
                    BRANCH_NAME == 'master' && CODE_CHANGES == true
                }
            }
            steps {
                echo 'building the application...'
            }
        }
        stage("test") {
            steps {
                when {
                    expression {
                        // this stage will only execute if the branch is 'master' or 'dev'
                        // if not, it will skip
                        BRANCH_NAME == 'master' || BRANCH_NAME == 'dev'
                    }
                }
                echo 'testing the application...'
            }
        }
        stage("deploy") {
            steps {
                echo 'deploying the application'
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

