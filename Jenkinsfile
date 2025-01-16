// pipeline {
//     agent any

//     stages {
//         stage('w/o docker') {
//             steps {
//                 sh '''
//                     echo "With Docker"
//                     ls -la 
//                     touch container-no.txt
//                 '''
//             }
//         }
//         stage('with docker') {
//             agent {
//                 docker {
//                     image 'node:18-alpine'
//                     reuseNode true 
//                 }
//             }
//             steps {
//                 script {
//                     // Running commands inside Docker container
//                     sh '''
//                         echo "With Docer"
//                         ls -la
//                         touch container-yes.txt
//                     '''
//                 }
//             }
//         }
//     }
// }
pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello MAMAMAMAMAMMAAM'
                sh 'echo "HELLO FROM SHELL"'
                echo 'HAHAHAHAHQWE'
                sh 'whoami'
            }
        }
    }
}
