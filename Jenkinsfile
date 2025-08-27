pipeline{
    agent{
        docker{
            image 'cypress/included:3.2.0'
            args 'entrypoint='     
        }
    }
    stages{
        stage("installation"){
            steps{
                sh 'npm ci'
            }
        }
        stage("run tests"){
            steps{
                sh 'npx cypress run'
            }
        }
    }
}