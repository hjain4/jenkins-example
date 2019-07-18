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
                unzip zipFile: Machine-Learning-A-Z-Q-A, dir: '${workspace}', quiet: true
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
