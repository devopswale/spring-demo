pipeline  {
  agent {
    node {
      label 'slave01'
}
}

  tools {
    maven 'maven3'

}

  options {
    buildDiscarder logRotator(
      daysToKeepStr: '5',
      numToKeepStr:  '10'

)
}
 environment {
    APP_NAME = "devopswale-demo"
    APP_ENV  = "dev"

}

stages {
   stage('clean workspace') {
    steps {
     cleanWs()
       sh """
        echo "clean the workspace for $APP_NAME"
        echo "we are in stage 1"
        """
         }
      }
  
  stage('Code Checkout') {
    steps {
     checkout([
        $class: 'GitSCM',
        branches: [[name: 'feature/jenkins']],
        userRemoteConfigs: [[credentialsId: 'ed841a8b-0508-4bdf-bef5-8f20d4524e60',url: 'https://github.com/devopswale/spring-demo.git']]])
    }
  }
  stage('list code') {
    steps {
   sh "ls -al" 
  }
  }
}
}
