pipeline {
    agent any
    
 stages {
        stage('Checkout') {
            steps {
             git credentialsId: '123', url: 'https://github.com/prajyotii/mainreport.git'
                }   
        }
         stage('Build') {
            steps {
             sh "mvn clean package"
            }   
        }
        stage('htmlreportonmail') {
            steps {
                
                publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: '/execution/node/3/ws/target/surefire-reports/', reportFiles: 'emailable-report.html', reportName: 'HTML Report', reportTitles: '', useWrapperFileDirectly: true])
                //publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'coverage', reportFiles: 'index.html', reportName: 'HTML Report', reportTitles: '', useWrapperFileDirectly: true])
                //http://localhost:8080/job/email/5/execution/node/3/ws/target/surefire-reports/emailable-report.html
            }   
        }
    }
}














