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
                    def rmImage = "docker rmi 4ea8165a149f"
                    def pullImage = "docker pull santana20095/react-nodejs:1.1"
                    def dockerCmd = "docker run -p 3080:3000 -d santana20095/react-nodejs:1.1"
                    sshagent(['ec2-server-key']) {
                    sh "ssh -o StrictHostKeyChecking=no ec2-user@13.39.146.56"
                    sh "${rmImage}"
                    sh "${pullImage}"
                }
                }
            }
        }               
    }
} 