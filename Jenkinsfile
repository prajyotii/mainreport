pipeline {

    agent any
    
    stages {

        stage('pull-code') {

            steps {
              git credentialsId: '123', url: 'https://github.com/prajyotii/mainreport.git'

            }

        }

        stage('build') {
          
             steps {
        
                sh "mvn clean package"
            
               }
          }
         stage('testNg') {
          
             steps {
        
                 testNG()
            
               }
         }
        stage('email')
        {
            steps { 
 emailext (to: 'prajyotifineshift@gmail.com', replyTo: 'prajyotifineshift@gmail.com', subject: "Email Report from - '${env.JOB_NAME}' ", body: readFile("target/surefire-reports/emailable-report.html"), mimeType: 'text/html');
            }
        }
    }
}
