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
                    sshagent(['ec2-server-key']) {
                    // sh "ssh -o StrictHostKeyChecking=no ec2-user@13.39.146.56"
                    sh "ssh -o StrictHostKeyChecking=no ec2-user@13.39.146.56 ${rmImage}"
                    sh "ssh -o StrictHostKeyChecking=no ec2-user@13.39.146.56  ${pullImage}"
                }
                }
            }
        }               
    }
} 