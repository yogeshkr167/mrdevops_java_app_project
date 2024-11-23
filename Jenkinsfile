@Library('my-shared-library') _

pipeline{

    agent any

    stages{
        stage('Git checkout'){
            steps{
            gitCheckout(
                branch: "main",
                url: "https://github.com/yogeshkr167/mrdevops_java_app_project.git"
            )
            }
        }

        stage('Unit Test Maven'){
            steps{
                script{
                    mvnTest()
                }
            
            }
        }

    }
}
