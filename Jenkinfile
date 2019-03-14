pipeline {
  agent any
  tools {
    nodejs "node"
  }
  //node {       
   //def workspace = pwd() 
  //}

  environment {
    CI = 'true' 
  }

  stages {
    
    stage('Checkout') {
      steps {
        git 'https://github.com/shashmca/testingMongodb.git'
      }
    }

    stage('server dependencies install') {
      steps {  
        //sh 'cd /var/jenkins_home/workspace/Capstone@script/capstone/api-server && npm install'    
        dir('testingMongodb') {
          sh 'npm install'
        }
      }
    }

    stage('server run') {
      steps {
        dir('testingMongodb') {
          sh 'npm start'
        }
        //sh 'cd /var/jenkins_home/workspace/Capstone@script/capstone/api-server && npm start'    
      }
    }
  }
}
    