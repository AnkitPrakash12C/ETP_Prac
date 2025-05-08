// pipeline{
//     agent any
//     stages {
//         stage('Build'){
//             steps{
//                 echo 'Building...'
//             }
//         }
//         stage('Test'){
//             steps{
//                 echo 'Testing'
//             }
//         }

//         stage('Deploy'){
//             steps{
//                 echo 'Deploying'
//             }
//         }
//     }
// }

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    docker.build('flaskapp')
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    docker.image('flaskapp').inside {
                        sh 'echo "No tests defined"' // Replace with actual test command
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    docker.image('flaskapp').run('-d -p 5000:5000 --name flaskapp_container')
                }
            }
        }
    }
}

