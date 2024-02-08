pipeline {
    agent {
        node {
            label 'agent-1'
        }      
    }
    environment { 
        greeting = 'morning'
    }
    options {
                timeout(time: 1, unit: 'SECONDS')
                disableConcurrentBuilds() 
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
                sh """
                    echo "running shell script"
                    echo "$greeting"
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
            echo 'runs when their is failure'
        }
        success { 
            echo 'runs when success!'
        }
    }
}


     
