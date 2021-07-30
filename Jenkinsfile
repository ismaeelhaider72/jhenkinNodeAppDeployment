pipeline {
  agent any
    
  stages {
        
    stage('Build') {
      steps {
        sh 'npm install'
         sh 'tar czf Node.tar.gz node_modules index.js package.json'
      }
    }  
    
    stage('Deploy') {
      steps {
        sshPublisher(publishers: [sshPublisherDesc(configName: 'ismaeelTesting', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '''sudo rm -r /var/www/
        sudo pkill node
        tar -xf  /home/ubuntu/test/Node.tar.gz
        node index.js > app.out.log 2> app.err.log < /dev/null & ''', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/test/', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '**/*.gz ')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])

        
      }
    } 
    
    
  }
}
