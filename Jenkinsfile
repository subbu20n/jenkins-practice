pipeline {
    agent {
        label 'AGENT-1'
    }
    environment {
        COURSE = "Jenkins"
    }
    stages{
        stage('Build'){
            steps {
                script{
                    echo "Building"
                    env
                }
            }    
        }
        stage('Test'){
            steps {
                script {
                      echo "Testing"
                }
            }

        }
        stage('Deploy'){
            steps {
                script {
                     echo "Deploy"
                }
            }
        }
    }
    post {
        always {
            echo "I will say always Hello Again!"
            deleteDir()
        }
        success {
            echo "Hello Success"
        }
        failure {
            echo "Hello Failure"
        }
    }
}