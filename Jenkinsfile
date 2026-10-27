pipeline{
    agent any
        stages{
            stage("Run App"){
                steps{
                    echo "Running the calculator application"
                    sh "python3 calc.py"
                }
            }
            stage("Run Tests"){
                steps{
                    echo "Running the tests"
                    sh "python3 test_calc.py"
                }
            }
            stage("Package Artifact"){
                steps{
                    echo "Zipping the verified code as artifact"
                    sh "python3 -m zipfile -c build-${BUILD_NUMBER}.zip *.py"
                    archiveArtifacts artifacts: "build-${BUILD_NUMBER}.zip"
                }
            }
        }
        post{
            always{
                cleanWs()
            }
            success{
                echo "pipeline succeeded, Build Number: ${BUILD_NUMBER}"
            }
            failure{
                echo "Pipeline failed. Please check the logs for errors."
            }
    }
}