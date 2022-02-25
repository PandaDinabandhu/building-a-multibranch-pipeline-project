pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'eckho "Hello world!"'
                echo "{$env.JOB_NAME}"
                echo "{$env.BRANCH_NAME}"
            }
        }
    }
    post{
    failure {  
        	script {	
        	if (env.JOB_NAME == "multi") {
        		emailext body: "<h2><u>[Status: FAILED] AQI-Monorepo-Autobuild</u></h2><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL of build: ${env.BUILD_URL} <br> Branch Name: ${env.BRANCH_NAME}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "[FAILED] -> ${env.JOB_NAME} | [Do-Not-Reply]", to: "dinabandhu.panda@hach.com";  
        		} 
        	else if (env.BRANCH_NAME == "development") {
          		emailext body: "<h2><u>[Status: FAILED] AQI-Monorepo-Autobuild</u></h2><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL of build: ${env.BUILD_URL} <br> Branch Name: ${env.BRANCH_NAME}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "[FAILED] -> ${env.JOB_NAME} | [Do-Not-Reply]", to: "dinabandhu.panda@hach.com";  
       			 }
             
            } 
        }
    }    
}
