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
      sh 'echo "Building an application"'
        sh 'pwd'
        sh 'date'
        sh 'ls -la'
    }
  }
  stage('Test') {
    steps{
    echo "Testing Application"
  }
}
    stage('Deploy') {
      steps{
        echo "Deploying application"
      }
    }
}
}
