pipeline {
    agent {
        label 'AGENT-1'
    }
    environment {
        COURSE = "Jenkins"
    }
    options {
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
    }
    stages{
        stage('Build'){
            steps {
                script{
                    sh """
                      echo "Building"
                      sleep 10
                      env
                    """
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
 