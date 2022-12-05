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
	   sh ' docker build -t nusanj/alianz:$BUILD_NUMBER .'           
        echo 'Build Image Completed'                
      }           
    }
	
 stage('Deploy') {
            steps {
                script{
                        docker.withRegistry('public.ecr.aws/j1y6k7y3/test-flightapi', 'ecr:eu-west-2') {
                    app.push("${env.BUILD_NUMBER}")
                    app.push("latest")
                    }
                }
}

}
