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
        sh 'sudo ssh ubuntu@34.200.240.146 sudo rm -rf /var/www/'
        sh 'sudo ssh ubuntu@34.200.240.146 sudo mkdir -p /var/www'
        sh 'sudo ssh ubuntu@34.200.240.146 sudo chmod -R 777 /var/www/'
        sh 'sudo scp /home/ismaeel/ismaee.txt ubuntu@34.200.240.146:/var/www'
      }
    } 
    
    
  }
}
