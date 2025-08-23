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
     parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password') 
    }
    stages{
        stage('Build'){
            steps {
                script{
                    sh """
                      echo "Building"   
                      sleep 10 
                      env
                      echo "Hello ${params.PERSON}"
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
            input {
                message "Should we continue?"
                ok "Yes, we should"
                submitter: "alice,bob" 
                parameters: [
                    string(name: 'PERSON', defaultValue: 'false', description: 'who should i say hell to?')
                ]
            }
            steps {
                script {
                    echo "{PERSON}, nice to meet you"
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
 