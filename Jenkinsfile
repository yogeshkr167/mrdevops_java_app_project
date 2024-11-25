@Library('my-shared-library') _

pipeline{

    agent any

    parameters{

        choice(name: 'action', choices: 'create\ndelete', description: 'Choose create /Destroy')
    }

    stages{

        stage('Git checkout'){
        when{ expression { params.action == 'create' } }
            steps{
            gitCheckout(
                branch: "main",
                url: "https://github.com/yogeshkr167/mrdevops_java_app_project.git"
            )
            }
        }

        stage('Unit Test Maven'){
        when{ expression { params.action == 'create' } }

            steps{
                script{
                    mvnTest()
                }           
            }
        }

        stage('Maven Integration test'){
        when{ expression { params.action == 'create' } }
            steps{
                script{
                    mvnIntegrationTest()
                }
            }
        }

        stage('Sonar Scan'){
        when{ expression { params.action == 'create' } }
            steps{
                script{
                    def SonarQubecredentialsId = 'sonar-api'
                    statiCodeAnalysis(SonarQubecredentialsId)
                }
            }
        }

        stage('Quality gates Status check'){
        when{ expression { params.action == 'create' } }
            steps{
                script{
                    def SonarQubecredentialsId = 'sonar-api'
                    waitForQualityGate(SonarQubecredentialsId)
                }
            }
        }
        stage('Maven build'){
        when{ expression { params.action == 'create' } }
            steps{
                script{
                    mvnBuild()
                }
            }
        }



    }
}