@Library('my-shared-library') _

pipeline{

    agent any

    parameters{

        choice(name: 'action', choice: 'create\ndelete', description: 'Choose cretae /Destroy')
    }

    stages{

        when{ expression { param.action == 'create' } }
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

        stage('Maven Integration test'){
            steps{
                script{
                    mvnIntegrationTest()
                }
            
            }
        }



    }
}
