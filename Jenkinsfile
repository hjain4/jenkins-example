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
                powershell ('Expand-Archive .\Machine-Learning-A-Z-Q-A.zip .\')
                }
                
            }
        }


        stage ('List Files') {
            steps {
                withMaven(maven : 'maven_3_5_0') {
                    sh 'mvn deploy'
                }
            }
        }
        stage ('Delete Files') {
            steps {
                withMaven(maven : 'maven_3_5_0') {
                    sh 'mvn deploy'
                }
            }
        }
        stage ('Mail Done') {
            steps {
                withMaven(maven : 'maven_3_5_0') {
                    sh 'mvn deploy'
                }
            }
        }
    }
}
