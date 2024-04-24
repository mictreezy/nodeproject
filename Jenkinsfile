pipeline {
  agent any

  stages {
    stage ('Build') {
      steps{
        script {
          //build docker image
          sh 'npm install'
        }
      }
    }
    stage ('Dockersize') {
      steps {
        script {
          //run docker container
          sh 'docker build -t emticzon30/mini-project .'
        }
      }
    }
    stage ('Push to Dockerhub'){
      steps {
        script {
          withCredentials([usernamePassword(usernameVariable: 'emticzon30', passwordVariable: 'passwordLOL')]) {
            sh "docker login -u $emticzon30 -p $passwordLOL"
            sh 'docker push emticzon30/mini-project'
        }
      }
    }
  }
}
}
