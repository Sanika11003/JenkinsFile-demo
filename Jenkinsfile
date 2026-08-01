pipeline {
  agent any
  stages {
    stage('Build') {
      steps{
      sh 'mvn clean compile'
    }
  }
  stage('Test') {
    steps{
    sh 'mvn test'
  }
}
    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }
    stage('Archive') {
      steps {
        archiveArtifacts artifacts: 'target/*.jar'
      }
    }

}
	post {
		always {
			echo 'Pipeline execution completed'
}
		success {
			echo 'Build, Test and Package Successful'
		}
		failure {
			echo 'Pipelinne Failed - check console output'
		}
	}
}
