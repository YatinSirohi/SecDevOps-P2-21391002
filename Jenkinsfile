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
