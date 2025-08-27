pipeline{
    agent{
        docker{
            image 'cypress/browsers:latest'
            args 'entrypoint='     
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
    post{
        always{
          
            // cucumber 'cypress/cucumber-json/*.json'
            sh 'tools/generate_html_cucumber_report.sh'
            archiveArtifacts 'cypress/screenshots/**, rapports/**'
            
            // publishHTML(target: [
            //     allowMissing: false,
            //     alwaysLinkToLastBuild: true,
            //     keepAll: true,
            //     reportDir: 'rapports/html',
            //     reportFiles: 'cucumber_report.html',
            //     reportName: 'Cucumber Report'
            // ])
        }
    }
}