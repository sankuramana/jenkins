// pipeline {
//     agent {
//         node{
//             label 'AGENT-1'
//         }
//     }
//     environment {
//          COURCE = "jenkins"
//     }
//     options {
//          timeout(time: 10, unit: 'MINUTES')
//            disableConcurrentBuilds()
//     }
//     parameters {
//         string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
//         text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
//         booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Toggle this value')
//         choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
//         password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
//     }
//     stages {
//         stage('Build') {
//             steps {
//                 script
//                 {
//                     sh """
//                 echo "building"
//                 echo $COURCE
//                 # sleep 10

//                         echo "Hello ${params.PERSON}"
//                         echo "Biography: ${params.BIOGRAPHY}"
//                         echo "Toggle: ${params.DEPLOY}"
//                         echo "Choice: ${params.CHOICE}"
//                         echo "Password: ${params.PASSWORD}"                
//                 env 
//                 """
//                 }
//             }
//         }
//         stage('Test') {
//             steps {
//                script
//                 {
//                     sh """
//                 echo "Testing"
//                 """
//                 }
//             }
//         }
//         stage('Deploy') {
//             steps {
//                script
//                 {
//                     sh """
//                 echo "Deploying"
//                 """
//                 }
//             }
//         }
//     }
//     post{
//         always{
//             echo " i will always say ello again!"
//             cleanWs() // for not getting claseh when you run agnain
//         }
//         success{

//             echo " i will run if success"
//         }
//         failure{

//             echo " i will run if failure"
//         }
//         aborted {
//              echo " pipeline is aborted"
//         }
//     }
// } 
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
            
        }
