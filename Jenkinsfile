pipeline{

    agent any

    stages{
        stage(' Git checkout '){
            steps{
                script{
                    
                    gitCheckout(
                        branch: "main"
                        url: "https://github.com/yogeshkr167/mrdevops_java_app_project.git"
                    )
                }
            }
        }
    }
}