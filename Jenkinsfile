@Library("shared-lib") _
pipeline {
    agent any
    tools {
        maven 'maven-version-3.9.12'
    }
    
    
    stages {
        stage('Hello')
        {
            steps{
                echo 'This is shared lib jenkins pipeline'
                script{
                    hello()
                }
            }
        }
        stage('Build') {
            steps {
                echo 'Building Java Project'
                bat 'mvn clean install'
            }
        }
        stage('Test')
        {
            steps{
                echo 'Test Result - JUint from surefire-reports'
                bat 'mvn test'
            }
            post{
                always{
                    junit '\\target\\surefire-reports\\*.xml'
                }
            }
        }
        stage('Deploy')
        {
            steps{
                echo 'Deploy on MultiCloud Env / On-Prem'
            }
            
        }
    }
}
