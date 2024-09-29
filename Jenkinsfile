pipeline {
  agent {
    docker { image 'node:16-alpine' 
             args '-u root'     //To run as a root               
            }
  }
  stages {
    stage('Install Dependencies') {
      steps {
        sh 'npm install --save'
      }
    }
  stage('Test') {
      steps {
        echo 'Testing...'
        snykSecurity(
          snykInstallation: 'yatin-snyk-api-token',
          snykTokenId: 'cc4f98bf-2f28-46ea-bfeb-0e1386afa726',
        )
      }
    } 
  }
  post {
        success {
            echo 'Pipeline built successfully!'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
