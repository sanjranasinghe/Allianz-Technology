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
        git([url: 'https://github.com/ismailyenigul/hacicenkins.git', branch: 'master', credentialsId: 'ismailyenigul-github-user-token'])
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
    
    
