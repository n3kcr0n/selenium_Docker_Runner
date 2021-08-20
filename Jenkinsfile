pipeline{
    agent any
    stages{
        stage("START GRID"){
            steps{
                sh "docker-compose up --no-color -d hub chrome firefox "
            }
        }
        stage("Run Test"){
            steps{
                sh "docker-compose up Search-module1 Search-module2 Flight-module1 Flight-module2"
            }
        }
    }
    post{
        always{
            archiveArtifacts artifacts: 'Test_Output/**'
            sh "docker-compose down"
        }
    }
}