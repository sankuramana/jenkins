pipeline {
    agent any
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
            echo " i will always say ello again"
        }
    }
}