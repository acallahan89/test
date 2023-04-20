pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/acallahan89/flasky', branch: 'main')
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t acallahan89/flask_app .'
      }
    }

    stage('Docker Login') {
      steps {
        sh 'docker login -u acallahan89 -p dckr_pat_g6JODr4A7hSYjNb9-NYeGmk3PLE'
      }
    }

    stage('Docker Push') {
      steps {
        sh 'docker push acallahan89/flask_app'
      }
    }

  }
}