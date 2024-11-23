pipeline{
    agent any

    stages{
        stage('Git checkout'){
            steps{
                script{
                    git branch: 'main', url: 'https://github.com/yogeshkr167/mrdevops_java_app.git'
                }
            }
        }
    }
}