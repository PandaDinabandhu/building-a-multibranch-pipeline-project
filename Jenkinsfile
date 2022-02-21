pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Hello world!"'
            }
        }
    }
    post {
        failure {  
        	script {	
        		if (BRANCH_NAME ==~ /(master)/ || ${env.JOB_NAME} == "multi") {
        		mail bcc: '', body: "<b>Example</b><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL de build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "ERROR CI: Project name -> ${env.JOB_NAME}", to: "dinabandhu.panda@hach.com";  
        	}
             
         } 
    } 
    
    }
}
