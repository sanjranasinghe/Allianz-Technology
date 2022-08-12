pipeline {
   agent any
   environment {     
    DOCKERHUB_CREDENTIALS= credentials('dockerhub')     
  }    
  stages {         
    stage("Git Checkout"){           
      steps{                
	   git branch: 'main', url: 'https://github.com/sanjranasinghe/Allianz-Technology.git'
	echo 'Git Checkout Completed'            
      }        
  }
   stage('Build Docker Image') {         
      steps{                
	   sh 'sudo docker build -t nusanj/alianz:$BUILD_NUMBER .'           
        echo 'Build Image Completed'                
      }           
    }
	
	stage('Login to Docker Hub') {         
      steps{                            
	sh 'echo $DOCKERHUB_CREDENTIALS_PSW | sudo docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'                 
	echo 'Login Completed'                
      }           
    }

stage('Push Image to Docker Hub') {         
      steps{                            
	sh 'sudo docker push nusanj/alianz:$BUILD_NUMBER'                 
	echo 'Push Image Completed'       
      }           
    }      	
}

}
