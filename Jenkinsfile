pipeline {

  agent any

  stages {

    stage('GIT CLONE') {
      steps {
        git 'https://github.com/AbbasAlip/Flask-Two-tier-application.git'
      }
    }

    stage('Build Docker Image') {
      steps {
        sh 'docker build -t flask-twotier .'
      }
    }

    stage(' Docker Compose') {
      steps {
        sh 'docker compose down || true'
        sh 'docker compose up -d --build'
      }
    }
  }
}
