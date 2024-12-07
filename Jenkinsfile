pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }

    environment {
        GREETING = 'HELLO JENKINS'
    }
     options {
        timeout(time: 1, unit: 'HOURS')
        disableConcurrentBuilds
    }
    // build
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
        stage('Deploy') {
            steps {
                sh """
                    echo "Here I wrote shell script"
                    echo "GREETING"
                    sleep 10
                """    
            }
        }
    }
    // post build
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure {
            echo 'this runs when pipeline is failed, used generally to send some alert'
        }
        success {
            echo 'I will say Hello when pipeline is success'
        }
    }
}