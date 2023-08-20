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

        stage('Test') {

            steps('SonarQube Analysis') {
                
                withSonarQubeEnv('sonarserver') {

                    sh "mvn sonar:sonar"

                }

            }
        }
    }
}
