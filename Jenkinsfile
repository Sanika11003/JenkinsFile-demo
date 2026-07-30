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
      echo "Building an application"
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
