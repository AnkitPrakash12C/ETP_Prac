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
                sh 'docker run --rm flaskapp echo "No tests defined"'  // Replace with real tests if needed
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker run -d -p 5000:5000 --name flaskapp_container flaskapp'
            }
        }
    }
}

