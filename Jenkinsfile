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
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }

            steps {
                sh '''
                    ls -la 
                    node --version
                    npm --version
                    npm ci 
                    npm run build
                    ls -la
                '''
            }
        }

        stage('Test') {
             agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh ''' 
                    test -f build/index.html
                    npm test
                '''
            }
        }

    
    }
    post {
        always{
            junit 'test-results/junit.xml'
        }
    }
}
