pipeline {
    agent any
    environment {
        AWS_ACCOUNT_ID="715451173743"
        AWS_DEFAULT_REGION="eu-west-2"
        IMAGE_REPO_NAME="jenkins-pipeline"
        IMAGE_TAG="v1"
        REPOSITORY_URI = "715451173743.dkr.ecr.eu-west-2.amazonaws.com"

    }
   
    stages {
        
         stage('Logging into AWS ECR') {
            steps {
                script {
                sh """aws ecr get-login --region eu-west-2 | docker login --username AWS -p p eyJwYXlsb2FkIjoicnZQUXN4MFRZWnNPaStONDZHZ3VDdWN6eW5jL1pzaElYSmhKMFlUQ1JScGtmT1dWSFJ4REV5c3pkSXBBQUxEck16OThFZEdFTXJWMGx3aW9ONmYwVHpoa3g3aU41K3MxdFo2am1TcDBjdlpGc2pzVzRSTU9KbnlOS21ZZnBnK0RzaGROYmNpZ2hFWnQzL2FqUXR5MTlXQkFyd0V0TzJ2RjNzRFJpcHRVY00xZVFxSUNyUWVHeEFpeFd1VWlpQ01VemJyOCtnSzI1WFd1T0VCaVFhNGNlTzNETjYzVzh0eVp3QnhvdWU0YXZsNUc3RnlnVXNpRWhxcXNrMHF3TkVwc1cydDJtSlMwUDByVG5HTXk5aWd0bC9kZnBub1hSNHk2VGZVQVhqN01wcFZ0cFo0a3pPanJJUjhGZVpnVkVwbVdJMjRGbUM1WnlYcStyRDFLUXVIMnBlYVRyV1JUZmNHQXJjQTVUbmVBSEdyMFVlN25kb0lhNkJicGhJYlNqd3pKYnp5RUhLSWJPSlFaclZacFpJTnJ4UHNySXdSZWJjMEJ4enlWYmYrb3Zja0JBSXJkNGp6VXp3b2gwenRuWUtlT3V2MFhFYVVVbWN0NFE3cGs0b0QrQUtoaHBlcE42aUJsNzI4V2Jwenk1dTV0dEV2MFBxQzRnc3FNWWNESGxQRDFBajlvMkY4d25hcUp4ZmlIbU4rV2hoanlDL3hocXhSczkvYWxxRTA5UEhVZWwyVmFQUmwvT2NVZWprNjYyaHlZY0N5dk5ndDE1Wm5KUVZUaXExdElFNURzbCt3K3djNmk2ajNjYkVZM3pzbldRdkVGSFU3ZDhZeTcrcjIxS081Ny9xOUdpSldDSVJpVm03bjExaEVSOW1tZHFHTlR0UFVMUlRRN1B4SXZxcTl0dW9adGdUZEFTQjFmYzd5dDZaWC9ML1hEUEhDVXIvWUhRaWJwNUNDTS81L3U5Q3cvSk03Wm9aWGpCTVh4VEs0S005ZW5XcUMxOE5WNXBqYS9ZSHlneTdKRzNzYVpIU2Ewd3VoTzlrN0p1SEI2azk3Q2YxRlY0cmx4eUtVQUV6RlNHTjNBY3d1T25KOGNocjQ2dk50YVQvdEMxdFczbmIxQ3dhNm55QVBWY2gxREZONXdvSWdySVhiWmlFY1ZIZ3UzZ1VUZE5KV2ZGTnhFKzdERitBQkFrL3FHblRCV1FZTDErUnlkeVI3OWlxc241M1ZFMmIwREdhY2lkMnhwOHpZdmJrZEFHM0RhbnpiUU16cjRxQkpFYnpablhVYTdUL0VPTEl1cnpWS0NVYVVlQjd3SXVPN2ZlN2NGWVowbS9PYjJrS0VGZXl5SnhXNytpdkVQRUR1a1B1QkN1OVlaT2p2Ris5ME04eGFTMzdZcVNzcVd3dzQ4S2NyNVNaM1Flc29COWh4ZlROQ1RtWHBtbnVSVzhxOWpPTFdXOVVXRm5OcXhYalNHZ24ramNVNDlFRzNHeWhPVkFjUDArbzYyUEdqLzhZMFphMTcvMUNPT3k3SmVjRXhicUcweDVad1BWMmI1NTB3Wmk5SHpQM25SRis5bWhJU2VabWlOdGVQQ2VFNU16RDk2YmE1MFlmamFwaTFINTUrVXBqbFFoYnJDbk9LcHQ4bjF6M1FvRlg3QU1jbmxKbU1mNmcweEdmZzRGbmhRblZJcm1vU2lNWnNQZDRJY3kzQ2lhbW5JMFdTeTM4T0liazNneVhGZEdVWWhXTzBUamMzTjh0TTNPRFl2dGlSdGNneGdBOGtpUUp2UVFQNk0xd0Jrc2M4VzYrTjhzTDJtVjJnSEovK0thZnZjTFgxVXVvcGI5V0h1RjFtK3FaMjNZTE91aVEzTnB3bz0iLCJkYXRha2V5IjoiQVFFQkFIaE5EeldWbllHeWxLM3RVYWxIQU5wbXJuUXphNXc0VzRjSFlNVTgydGJOSXdBQUFINHdmQVlKS29aSWh2Y05BUWNHb0c4d2JRSUJBREJvQmdrcWhraUc5dzBCQndFd0hnWUpZSVpJQVdVREJBRXVNQkVFREp6cWkvMVZTWkdicnhYT1hRSUJFSUE3c3prWWtyVkdYVklYTzFyWUNjRWZ2dmpXZmRBM2RaYk1waWFRQzlaUGJwU1VNUXhkenVGVXd0d0JrQWJUcG4vZWxrOU9YcWZ0MVdocjlRQT0iLCJ2ZXJzaW9uIjoiMiIsInR5cGUiOiJEQVRBX0tFWSIsImV4cGlyYXRpb24iOjE2NzAzNjU1OTV9 715451173743.dkr.ecr.eu-west-2.amazonaws.com 715451173743.dkr.ecr.eu-west-2.amazonaws.com"""
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
