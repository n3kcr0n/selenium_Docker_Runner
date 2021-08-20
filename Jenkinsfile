pipeline{
    agent any
    stages{
        stage("START GRID"){
            steps{
                sh "docker-compose up -d hub chrome firefox"
            }
        }
        stage("Run Test"){
            steps{
                sh "docker-compose up search-module Flight-module"
            }
        }
        stage("Stop Grid"){
            steps{
                sh "docker-compose down"
            }
        }   
    }
}