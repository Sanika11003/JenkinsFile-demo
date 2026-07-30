pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        echo "Downloading Code"
      }
    }
    stage('Build') {
      steps{
     sh 'echo "Hello jenkins" > output.txt'
     sh 'cat output.txt'
    }
  }
  stage('Test') {
    steps{
    echo "Testing Application"
  }
}
    stage('Archive') {
      steps {
        archiveArtifacts artifacts: 'output.txt'
      }
    }
    stage('Deploy') {
      steps{
        echo "Deploying application"
      }
    }
}
}
