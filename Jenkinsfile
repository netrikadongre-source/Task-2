pipeline {
  agent any

  environment {
    IMAGE_NAME = "netrika0210/jenkins-node-app"
  }

  stages {
    stage('Build Docker Image') {
      steps {
        script {
          docker.build("${IMAGE_NAME}")
        }
      }
    }

    stage('Push to DockerHub') {
      steps {
        withDockerRegistry([credentialsId: 'netrika0210', url: '']) {
          script {
            docker.image("${IMAGE_NAME}").push("latest")
          }
        }
      }
    }
  }
}

