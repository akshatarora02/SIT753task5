pipeline {
  agent any
  
  environment {
    DIRECTORY_PATH = "/Users/akshatarora/.jenkins/jobs/"
    TESTING_ENVIRONMENT = "dev"
    PRODUCTION_ENVIRONMENT = "Akshat"
  }
  
  stages {
    stage('Build') {
      steps {
        echo "Fetching source code from ${env.DIRECTORY_PATH}"
        echo "Compiling the code and generating artifacts"
      }
    }
    
    stage('Test') {
      steps {
        echo "Running unit tests"
        echo "Running integration tests"
      }
    }
    
    stage('Code Quality Check') {
      steps {
        echo "Checking the quality of the code"
      }
    }
    
    stage('Deploy') {
      steps {
        echo "Deploying the application to ${env.TESTING_ENVIRONMENT} environment"
      }
    }
    
    stage('Approval') {
      steps {
        sleep 10
      }
    }
    
    stage('Deploy to Production') {
      steps {
        echo "Deploying the code to the ${env.PRODUCTION_ENVIRONMENT} environment"
      }
      post {
        success {
          mail to: "akshatarora028@gmail.com",
          subject: "Build and deployment successful!",
          body: "Build and deployment to production was successful."
        }
      }
    }
  }
}
