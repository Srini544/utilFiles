def callCurlCommand() {
    echo 'calling curl .... '
}

pipeline {
    
  environment {
    registry = "raghupatruni/srini7"
    registryCredential = 'dockerhub'
  }
    options {
        timestamps()
    }
    agent { dockerfile true
          }
        
    stages {
        stage('code') {
            steps {
                echo 'code completed .... '
                //sh 'setMe.sh'
                //callCurlCommand()
            }
        }
        stage('build') {
            steps {
                echo 'build completed .... '
                dockerImage = docker.build registry + ":$BUILD_NUMBER"
            }
        }    
        stage('deploy') {
            steps {
                echo 'deploy completed .... '
            }
        }
        stage('test') {
            steps {
                echo 'build completed .... '
            }
        }
        stage('push to hub') {
            steps {
                script {
                    docker.withRegistry( '', registryCredential ) {
                    dockerImage.push()
                    }
                }
            }
        }
    }
}
