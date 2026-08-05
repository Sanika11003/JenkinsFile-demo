pipeline {
 
    agent any
 
    parameters {
 
        choice(
            name: 'ENV',
            choices: ['DEV','QA','PROD'],
            description: 'Select Environment'
        )
 
        booleanParam(
            name: 'DEPLOY',
            defaultValue: true,
            description: 'Deploy Application'
        )
 
    }
 
    stages {
 
        stage('Checkout') {
            steps {
                echo "Checking out code from GitHub..."
            }
        }
 
        stage('Clean') {
            steps {
                sh 'mvn clean'
            }
        }
 
        stage('Compile') {
            steps {
                sh 'mvn compile'
            }
        }
 
        stage('Test') {
            steps {
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
 
        stage('Approval') {
 
            when {
                expression {
                    return params.DEPLOY
                }
            }
 
            steps {
                input message: "Deploy to ${params.ENV} ?", ok: "Deploy"
            }
        }
 
        stage('Deploy') {
 
            when {
                expression {
                    return params.DEPLOY
                }
            }
 
            steps {
 
                script {
 
                    if(params.ENV=="PROD"){
 
                        echo "Deploying to Production..."
 
                    }
 
                    else{
 
                        echo "Deploying to ${params.ENV}"
 
                    }
 
                }
 
            }
 
        }
 
    }
 
    post {
 
        success {
 
            echo "Pipeline Completed Successfully"
 
        }
 
        failure {
 
            echo "Pipeline Failed"
 
        }
 
        always {
 
            echo "Pipeline Finished"
 
        }
 
    }
 
}
