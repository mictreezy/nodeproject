pipeline {
  agent any

  stages {
    stage ('Build') {
      steps{
        script {
          //build docker image
          sh 'docker build -t mini-project .'
        }
      }
    }
    stage ('Deploy') {
      steps {
        script {
          //run docker container
          sh 'docker run -d -p 3000:3000 mini-project'
        }
      }
    }
  }
}
