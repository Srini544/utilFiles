pipeline {
    agent any
  environment {
    registry = "raghupatruni/srini7"
    registryCredential = 'dockerhub'
  }
  stages {
    
    stage('Building image') {
      steps{
        script {
            docker.withRegistry( '', registryCredential ) {
            docker.build("raghupatruni", "--no-cache -f Dockerfile .").push()
          dockerImage = docker.build registry + ":$BUILD_NUMBER"
            }
        }
      }
    }
    
    stage('Deploy Image') {
      steps{
        script {
          docker.withRegistry( '', registryCredential ) {
            dockerImage.push()
          }
        }
      }
    }
    stage('Remove Unused docker image') {
      steps{
        sh "docker rmi $registry:$BUILD_NUMBER"
      }
    }
    
  }
}
