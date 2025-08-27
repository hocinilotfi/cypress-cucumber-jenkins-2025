pipeline{
    agent{
        docker{
            image 'cypress/browsers:latest'
            args '--entrypoint=' 
        }
    }
    stages{
        stage('Node Version') {
            steps {
                 sh 'node --version'
            }
        }
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