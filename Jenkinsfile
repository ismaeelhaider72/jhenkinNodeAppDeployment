pipeline {
  agent any
    
  tools {nodejs "NodeJS"}
    
  stages {
        
    stage('Git') {
      steps {
        git 'https://github.com/ismaeelhaider72/jhenkinNodeAppDeployment.git'
      }
    }
     
    stage('Build') {
      steps {
        sh 'npm install'
         sh 'tar czf Node.tar.gz node_modules index.js package.json'
      }
    }  
    
    stage('Deploy') {
      steps {
        sh 'sh ubuntu@34.200.240.146 rm -rf /var/www/'
         sh 'ssh ubuntu@34.200.240.146 mkdir -p /var/www/temp_deploy'
      }
    } 
    
    
  }
}
