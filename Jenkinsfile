def callCurlCommand{
    echo 'calling curl .... '
    sh("curl -s google.com")
}

pipeline {
    agent any
    options {
        timestamps()
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