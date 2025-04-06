#!/usr/bin.env groovy

pipeline {   
    agent any
    stages {
        stage("test") {
            steps {
                script {
                    echo "Testing the application..."

                }
            }
        }
        stage("build") {
            steps {
                script {
                    echo "Building the application..."
                }
            }
        }
        stage("deploy") {
            steps {
                script {
                    def rmImage = "docker rmi santana20095/react-nodejs:1.0"
                    def pullImage = "docker pull santana20095/react-nodejs:1.1"
                    def dockerCmd = "docker run -p 3080:3080 -d santana20095/react-nodejs:1.1"
                    
                    sshagent(['ec2-server-key']) {
                    // sh "ssh -o StrictHostKeyChecking=no ec2-user@13.39.146.56 ${rmImage}"
                    sh "ssh -o StrictHostKeyChecking=no ec2-user@13.39.146.56  ${pullImage}"
                    sh "ssh -o StrictHostKeyChecking=no ec2-user@13.39.146.56  ${dockerCmd}"
                }
                }
            }
        }               
    }
} 