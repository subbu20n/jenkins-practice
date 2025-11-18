pipeline {
    agent {
        label 'AGENT-1'
    }
    environment {
        course = "jenkins"
    }
    options {
        timeout(time:10, unit: 'SECONDS')
    }
    stages {
        stage ('Build') {
            steps {
                script {
                    sh """
                      echo "Building.."
                      sleep 10 
                      env 
                    """   
                } 
            }
        }
        stage ('Test') {
            steps {
                script {
                  echo "Testing.."
                } 
            }
        }
        stage ('Deploy') {
            steps {
                script {
                  echo "Deploying.."
                }   
            }
        }
    }
    post {
        always {
            echo "I will say hello again!" 
            /* deleteDir() */
        }
        success {
            echo "Hello Success"
        }
        failure {
            echo "Hello Failure"
        }
    }
}