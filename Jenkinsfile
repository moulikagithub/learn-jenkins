pipeline {
    agent {
        node {
            label 'agent-1'
        }      
    }
    // build
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
// post build
 post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure { 
            echo 'this runs when pipeline fails ,generally used to send alert incase of failure'
        }
        success { 
            echo 'this runs when pipeline is success'
        }
    }
