pipeline {
  environment {
    imagename = "nusanj/jenkins"
    registryCredential = 'nusanj-Nuribaba@123'
    dockerImage = ''
  }
  
   agent any
  stages {
    stage('Cloning Git') {
      steps {
        git([url: 'https://github.com/sanjranasinghe/Allianz-Technology.git', branch: 'main', credentialsId: '	c535657d-2c30-46b9-93c5-6fdcea0381ff'])
      }
      }
      }
        stage('Building image') {
      steps{
        script {
          dockerImage = docker.build imagename
        }
      
      }
    }
    }
    
    
