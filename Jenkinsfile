pipeline{
    agent any
    stages{
        stage("Cleanup"){
            steps{
                sh '''
                    docker ps -a --filter "ancestor=anu_project" --format "{{.ID}}" | xargs docker stop
                    docker rmi -q anu_project | xargs -r rmi -f
                '''
            }
        }
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
