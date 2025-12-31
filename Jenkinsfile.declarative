pipeline {
    agent {
        node{
            label 'AGENT-1'
        }
    }
    stages {
        stage('Build') {
            steps {
                echo "building"
            }
        }
        stage('Test') {
            steps {
                echo "Testing"
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploye"
            }
        }
    }
    post{
        always{
            echo " i will always say ello again!"
            cleanWs() // for not getting claseh when you run agnain
        }
        success{

            echo " i will run if success"
        }
        failure{

            echo " i will run if failure"
        }
    }
}