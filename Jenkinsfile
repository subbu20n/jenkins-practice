pipeline {
    agent {
        label 'AGENT-1'
    }
    stages{
        stage('Build'){
            steps {
                echo "Building"
            }    
        }
        stage('Test'){
            steps {

                echo "Testing"
            }

        }
        stage('Deploy'){
            steps {
                echo "Deploy"
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