pipeline{
    agent any
    stages{
        stage("Build_Image"){
            steps{
                sh 'docker build -t anu_project .'
            }
        }
        stage("Production"){
            steps{
                sh 'docker run -it -d -p 8085:80 anu_project'
            }
        }
    }
}
