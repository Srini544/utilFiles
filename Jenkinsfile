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
                //sh 'setMe.sh'
                //callCurlCommand()
            }
        }
        stage('build') {
            steps {
                echo 'build completed .... '
                app = docker.build('raghpatruni/srini7')
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
                echo 'image pushed ...1. '
                docker.withRegistry('https://cloud.docker.com','dockerhub')
                echo 'image pushed ...2. '
                docker.push('latest')
                echo 'image pushed ...3. '
                echo 'image pushed ...4. '
                echo 'image pushed ...5. '
            }
        }
    }
}
