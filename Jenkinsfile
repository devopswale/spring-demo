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
      
}
}
   stage('Code Checkout to Source code Repo') {
    steps {     
     checkout scm
}
}
}
}
