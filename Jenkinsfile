pipeline {
    agent {
        node{
            label 'AGENT-1'
        }
    }
    environment {
         COURCE ="jenkins"

    }
      options {
        timeout(time: 10, unit: 'MINUTES') 
        disableConcurrentBuilds()
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    // this is build section
    stages {
        stage('Build') {
            steps {
                script{

                
                sh """
                echo "building"
                env
                
                        echo "Hello ${params.PERSON}"
                        echo "Biography: ${params.BIOGRAPHY}"
                        echo "Toggle: ${params.DEPLOY}"
                        echo "Choice: ${params.CHOICE}"
                        echo "Password: ${params.PASSWORD}"
                sh """
                }
            }
        }
        stage('Test') {
            steps {
                script{
                sh """
                
                echo "Testing"
                sh """
                }
            }
        }
        stage('Deploy') {
            //  input { //taking input and from user and prceed deploye 
            //     message "Should we continue?"
            //     ok "Yes, we should."
            //     submitter "alice,bob"
            //     parameters {
            //         string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
            //     }
             when { 
                expression { "$params.DEPLOY" == "true" }
            }
            }
            steps {
                script{
                sh """
                echo "Deploye"
                sh """
                }
            }
        }
    }
    post{
        always{
            echo " i will always say ello again!"
            cleanWs()
            
        }
        success {
            echo "hello i will run when pipeline success"
        }
        failure{
            echo "hello iwill run if pipeline failure"
        }
        aborted {
            echo 'pipeline is aborted'
        }
    }
