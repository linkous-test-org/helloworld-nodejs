pipeline {
  agent none
  stages {
    stage('Test') {
      agent {
        kubernetes {
          yamlFile 'nodejs-pod.yaml'
        }
      }

      steps {
        sh 'java -version'
        container('nodejs') {
          echo 'Hello World!'   
          sh 'node --version'
        }
      }
    }
    stage('Build and Push Image') {
        when {
          beforeAgent true
          branch 'main'
        }
        steps {
          echo "TODO - build and push image"
        }
    }
  }
}
