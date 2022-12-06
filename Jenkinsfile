pipeline {
    agent any
    environment {
        AWS_ACCOUNT_ID="715451173743"
        AWS_DEFAULT_REGION="eu-west-2"
        IMAGE_REPO_NAME="jenkins-pipeline"
        IMAGE_TAG="v1"
        REPOSITORY_URI = "715451173743.dkr.ecr.eu-west-2.amazonaws.com
"
    }
   
    stages {
        
         stage('Logging into AWS ECR') {
            steps {
                script {
                sh """aws ecr get-login --region eu-west-2 | docker login --username AWS --password-stdin 715451173743.dkr.ecr.eu-west-2.amazonaws.com"""
                }
                 
            }
        }
        
        stage('Cloning Git') {
            steps {
                  git branch: 'main', url: 'https://github.com/sanjranasinghe/Allianz-Technology.git'
            }
        }
  
    // Building Docker images
    stage('Building image') {
      steps{
        script {
          dockerImage = docker.build "${IMAGE_REPO_NAME}:${IMAGE_TAG}"
        }
      }
    }
   
    // Uploading Docker images into AWS ECR
    stage('Pushing to ECR') {
     steps{  
         script {
                sh """docker tag ${IMAGE_REPO_NAME}:${IMAGE_TAG} ${REPOSITORY_URI}:$IMAGE_TAG"""
                sh """docker push ${AWS_ACCOUNT_ID}.dkr.ecr.${AWS_DEFAULT_REGION}.amazonaws.com/${IMAGE_REPO_NAME}:${IMAGE_TAG}"""
         }
        }
      }
    }
}
