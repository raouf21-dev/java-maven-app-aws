pipeline {
    agent none
    stages {
        stage('build') {
            steps {
                script {   
                    echo "Building the application..."   
                    echo "Branch $BRANCH_NAME" 
                }
            }
        }
        stage('test') {
            when {
                expression {
                    BRANCH_NAME == 'master'
                }
            }
            steps {
                script {
                    echo "Testing the application..."
                }
            }
        }
        stage('deploy') {
            steps {
                script {
                    echo "Deploying the application..."
                }
            }
        }
    }
}
