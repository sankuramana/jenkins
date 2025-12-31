pipeline {
    agent {
        node{
            label 'AGENT-1'
        }
    }
    environment {
         COURCE = "jenkins"
    }
    stages {
        stage('Build') {
            steps {
                script
                {
                    sh """
                echo "building"
                echo $COURCE
                env
                """
                }
            }
        }
        stage('Test') {
            steps {
               script
                {
                    sh """
                echo "Testing"
                """
                }
            }
        }
        stage('Deploy') {
            steps {
               script
                {
                    sh """
                echo "Deploying"
                """
                }
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