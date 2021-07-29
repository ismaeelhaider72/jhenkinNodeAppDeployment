pipeline {
  agent any
    
  tools {nodejs "NodeJS"}
    
  stages {
        
    stage('Git') {
      steps {
        git  'https://github.com/ismaeelhaider72/jhenkinNodeAppDeployment.git'
        sh 'npm install'
      }
    }
    
    stage('Code') {
      steps {
        sh 'echo “Run some lints”'
      }
    }    
    
    stage('Build') {
      steps {
        sh 'npm run clean’'
         sh 'npm run build'
      }
    }  
    
    stage('Deploy') {
      steps {
        sh 'sudo ssh ubuntu@34.200.240.146 sudo rm -rf /var/www/'
        sh 'sudo ssh ubuntu@34.200.240.146 sudo mkdir -p /var/www'
        sh 'sudo ssh ubuntu@34.200.240.146 sudo chmod -R 777 /var/www/'
        sh 'sudo scp dist ubuntu@34.200.240.146:/var/www'
      }
    } 
    
    
  }
}
