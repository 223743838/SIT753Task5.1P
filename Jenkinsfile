pipeline{
    agent any
        environment {
        DIRECTORY_PATH = '/SIT753/JenkinsFile'             
        TESTING_ENVIRONMENT = 'TESTING ENVIRONMENT'  
        PRODUCTION_ENVIRONMENT = 'PRODUCTION ENVIRONMENT'
    }
    stages{
        stage("Build"){
            steps{
                echo "fetch the source code from the directory path specified by the environment variable: ${env.DIRECTORY_PATH}"
                echo "compile the code and generate any necessary artifacts"
            }
        }
         stage("Test"){
            steps{
                echo "unit tests"
                echo "integration tests"
            }
        }
        stage("Code"){
            steps{
                echo "check the quality of the code"
            }
        }
        stage("Deploy"){
            steps{
                echo "deploy the application to a testing environment specified by the environment variable: ${env.TESTING_ENVIRONMENT}"
            }
        }
        stage('Approval') {
            steps {
                echo "Waiting for approval"
                sleep(time: 10, unit: 'SECONDS')
                echo "Approval received, continuing to deployment"
            }
        }
        
        stage('Deploy to Production') {
            steps {
                echo "Deploy the code to the production environment: ${env.PRODUCTION_ENVIRONMENT}"
            }
        }
            
    }

    
}