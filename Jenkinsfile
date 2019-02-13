pipeline {
    agent { docker { image 'android-sdk:latest' } }
    stages {
        stage('Build') {
            steps {
                sh 'whoami'
            }
        }
        stage('Upload') {
            steps {
              timeout(time: 5, unit: 'MINUTES') {
                  sh 'printenv'
              }
            }
        }
        stage('Test') {
            steps {
              sh 'ls'
            }
        }
    }
    post {
        always {
            echo 'One way or another, I have finished'
            deleteDir() /* clean up our workspace */
        }
        success {
            echo 'I succeeeded!'
        }
        unstable {
            echo 'I am unstable :/'
        }
        failure {
            echo 'I failed :('
        }
        changed {
            echo 'Things were different before...'
        }
    }
}
