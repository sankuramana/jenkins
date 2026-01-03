pipeline {
    agent {
        node{
            label 'AGENT-1'
        }
    }
    environment {
         COURCE ="jenkins"

    }
    stages {
        stage('Build') {
            steps {
                script{

                
                sh """
                echo "building"
                env
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
    }
}