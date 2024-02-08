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
                timeout(time: 1, unit: 'HOURS')
                disableConcurrentBuilds() 
            }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
                    #sleep 10
                """
            }
        }
        stage('check params') {
            steps {
                sh """
                    echo "HELLO ${params.PERSON}"
                    echo "Biography: ${params.BIOGRAPHY}"
                    echo "Toggle: ${params.TOGGLE}"
                    echo "Choice: ${params.CHOICE}"
                    echo "Password: ${params.PASSWORD}"
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


     
