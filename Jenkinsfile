
pipeline {
  agent { label 'agent-1' }
  stages {
    stage('Checkout') {
      steps {
        git branch: 'master',
        credentialsId: 'github-credentials',
        url: 'https://github.com/user/repo.git'
      }
    }
    stage('Build') {
      steps {
        sh 'mvn clean install'
      }
    }
    stage('Archive') {
      steps {
        archiveArtifacts artifacts: 'target/*.jar',
        fingerprint: true
      }
    }
  }
}

