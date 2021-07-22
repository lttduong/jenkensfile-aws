
CODE_CHANGES = getGitChanges()
pipeline{
    agent any
    environment {
        NEW_VERSION = "1.3.0"
        SERVER_CREDENTIALS = credentials('')
    }
    stages{
        stage("build"){
            when {
                expression {
                    BANCH_NAME =="dev" || CODE_CHANGES == true
                }
            }
            steps{
                echo "building the application"
                echo "building version ${NEW_VERSION}"
            }
            post{
                always{
                    echo "========always========"
                }
                success{
                    echo "========A executed successfully========"
                }
                failure{
                    echo "========A execution failed========"
                }
            }
        }
    }
    stages{
        stage("test"){
            when {
                expression {
                    BANCH_NAME =='dev' || BANCH_NAME == 'master'
                }
            }
            steps{
                echo "testing the application"
            }
            post{
                always{
                    echo "========always========"
                }
                success{
                    echo "========A executed successfully========"
                }
                failure{
                    echo "========A execution failed========"
                }
            }
        }
    }
    stages{
        stage("deploy"){
            steps{
                echo "deploying the application"
                echo "deploying with ${SERVER_CREDENTIALS}"
            }
            post{
                always{
                    echo "========always========"
                }
                success{
                    echo "========A executed successfully========"
                }
                failure{
                    echo "========A execution failed========"
                }
            }
        }
    }
    post{
        always{
            echo "========always========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}
