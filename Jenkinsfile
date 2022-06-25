pipeline {
  agent any 
  environment {
    AWS_ACCOUNT_ID="360802824704" 
    AWS_DEFAULT_REGION="ap-south-1"
   image_repo_name="dockerrjenkins"
    IMAGE_TAG="latest"
    REPOSITORY_URI = "${AWS_ACCOUNT_ID}.dkr.ecr.${AWS_DEFAULT_REGION}.amazon.com/${IMAGE_REPO_NAME}"
  }
    stages {
  stage('cloning Git') {
    steps {
      checkout scm
    }
  }

  stage('Building image') {
    steps{
      script {
        dockerImage = docker.build "${IMAGE_REPO_NAME}:${IMAGE_TAG}"
      }
    }
  }

  stage('pushing to ECR') {
    steps{
      script {
        docker.withRegistry(
          'https://<AWS_ACCOUNT_ID>.dkr.ecr.<AWS_DEFAULT_REGION>.amazonaws.com/<image_repo_name>') {
            def dockerImage = docker.build('image_repo_name')
            dockerImage.push('IMAGE_TAG')
          }
        }
      }
    }
  }
}
