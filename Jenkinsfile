pipeline{
    agent any
    stages{
        stage("Build_Image"){
            steps{
                sh 'docker build -t my_project .'
            }
        }
        stage("Production"){
            steps{
                sh 'docker run -it -d -p 8084:80 my_project'
            }
        }
    }
}
