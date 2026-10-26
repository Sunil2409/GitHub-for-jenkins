pipeline{
    agent any
        stages{
            stage("Clean Up"){
                steps{
                    echo "Cleaning up the workspace"
                    sh "rm -rf *"
                }
            }
            stage("Checkout Code"){
                steps{
                    git clone "https://github.com/Sunil2409/GitHub-for-jenkins.git"
                }
            }
            stage("Run App"){
                steps{
                    echo "Running the calculator application"
                    sh "python3 calculator/calc.py"
                }
            }
            stage("Run Tests"){
                steps{
                    echo "Running the tests"
                    sh "python3 calculator/test_calc.py"
                }
            }
            stage("Package Artifact"){
                steps{
                    echo "Zipping the verified code as artifact"
                    sh "zip build-${BUILD_NUMBER}.zip calculator/*.py"
                    archiveArtifacts artifacts: 'build-${BUILD_NUMBER}.zip'
                }
            }
        }
        post{
            success{
                echo "pipeline succeeded, Build Number: ${BUILD_NUMBER}"
            }
            failure{
                echo "Pipeline failed. Please check the logs for errors."
            }
    }
}