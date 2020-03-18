pipeline {
  agent {
    node {
      label 'master'
    }
  }
  stages {
    stage('Build result') {
      steps {
        sh 'docker build -t hayoade1/nextgeniam ./result'
      }
    } 
    stage('Build vote') {
      steps {
        sh 'docker build -t hayoade1/nextgeniam ./vote'
      }
    }
    stage('Build worker') {
      steps {
        sh 'docker build -t hayoade1/nextgeniam ./worker'
      }
    }
    stage('Push result image') {
      when {
        branch 'master'
      }
      steps {
        withDockerRegistry(credentialsId: 'docker-hub-credential', url:'https://index.docker.io/v1/') {
          sh 'docker push hayoade1/nextgeniam'
        }
      }
    }
    stage('Push vote image') {
      when {
        branch 'master'
      }
      steps {
        withDockerRegistry(credentialsId: 'docker-hub-credential', url:'https://index.docker.io/v1/') {
          sh 'docker push hayoade1/nextgeniam'
        }
      }
    }
    stage('Push worker image') {
      when {
        branch 'master'
      }
      steps {
        withDockerRegistry(credentialsId: 'docker-hub-credential', url:'https://index.docker.io/v1/') {
          sh 'docker push hayoade1/nextgeniam'
        }
      }
    }
  }
}
