PROJECT_RECIPIENT_LIST = 'himanshu.jain@outlook.com'

pipeline {
    agent any
    parameters {
     string(defaultValue: "TEST", description: 'What environment?', name: 'userFlag')
    }
    stages {
        stage ('Download') {

            steps {
                echo "${params.name}"
               
                   git url: 'https://github.com/hjain4/jenkins-example.git'
                powershell 'Write-Output "Hello, World!"'
               
            }
        }

        stage ('Unzip') {

            steps {
                
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
                script {
                powershell ('Expand-Archive .\\Machine-Learning-A-Z-Q-A.zip .\\')
                }
                
            }
        }


        stage ('List Files') {
            steps {
                 powershell ('ls')
               
            }
        }
        stage ('Delete Files') {
            steps {
                  powershell ('Remove-Item .\\Machine-Learning-A-Z-Q-A.zip')
            }
        }
        stage ('Mail Done') {
            steps {
                
                
               
                   emailext body: 'A Test EMail',recipientProviders: [[$class: 'PROJECT_RECIPIENT_LIST']], subject: 'Test'
                       
                
          
            }
        }
    }
}
