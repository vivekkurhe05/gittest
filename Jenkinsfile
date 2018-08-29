pipeline{
    agent any
    stages{
        stage('build'){
            steps{
                echo "This is a build phase"
            }
        }

        stage('Test'){
            steps{
                echo "This is a testing phase"
            }
        }

        stage('Deploy'){
            steps{
                echo "This is Deployment phase"
            }
        }

        stage('One'){
            steps{
                echo "This is test jenkinsfile"
            }
        }

        stage('Two'){
            steps{
                input('Do you want to proceed?')
            }
        }

        stage('Three'){
            when{
                not{
                    branch 'master'
                }
            }
            steps{
                echo "Hello!!!"
            }
        }

        stage('Four'){
            parallel{
                stage('Unit Test'){
                    steps{
                        echo "Running the unit tests..."
                    }
                }

                stage('Integration Test'){
                   agent{
                       docker{
                           reuseNode false
                           image 'ubuntu'
                       }
                   }
                   steps{
                       echo "Running the Integration tests..."
                   }
                }
            }
        }
    }
}