def callCurlCommand() {
    echo 'calling curl .... '
}

pipeline {
    
    options {
        timestamps()
    }
    agent { dockerfile true
          }
        
    stages {
        stage('code') {
            steps {
                echo 'code completed .... '
                callCurlCommand()
            }
        }
        stage('build') {
            steps {
                echo 'build completed .... '
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
    }
}
