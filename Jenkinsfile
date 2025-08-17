pipeline {
    agent {
        label 'AGENT-1'
    }
    environment {
        COURSE = 'jenkins'
    }
    
    // Build 
    stages {
        stage('Build') {
            steps {
                script {
                    sh """
                     echo "Building.."
                     env
                    """ 
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    echo "Testing.."
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    echo "Deploying.."
                }
            }
        }
    }
    post {
        always {
            echo "I will always say Hello Again!"
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
