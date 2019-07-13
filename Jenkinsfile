pipeline {
    agent any

    stages {
        stage ('Download') {

            steps {
               
                   git url: 'https://github.com/hjain4/jenkins-example.git'
               
            }
        }

        stage ('Unzip') {

            steps {
                
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
                
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
