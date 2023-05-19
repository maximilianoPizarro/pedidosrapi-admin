pipeline {
    agent {
        node {
            label 'nodejs'
            customWorkspace '/tmp/workspace/pedidosrapi-admin'
        }
    }
  stages {
        
    stage('Git') {
      steps {
        git branch: 'master', url: 'https://github.com/maximilianoPizarro/pedidosrapi-admin'
      }
    }
 
    stage('Install') {
      steps {
        sh "npm install"
      }
    }   
      
    stage('Build') {
        agent {
            node {
                label 'maven'
                customWorkspace '/tmp/workspace/pedidosrapi-admin'
            }
        }        
      steps {
        sh "mvn -Pprod clean verify"
      }
    }      
        
  }
}
