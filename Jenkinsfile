def gv
pipeline {
  agent any
  /*environment {
   # NEW_VERSION = '1.3.0'
    #SERVER_CREDENTIALS = credentials('server-credentials')
  }*/
  parameters {
    choice(name: 'VERSION', choices: ['1.1.0', '1.2.0'], description: '')
  }
  stages {
    stage("init"){
      steps {
        script {
          gv = load "script.groovy"
        }
        }
        }
    stage("build"){
      steps {
        /*echo 'building the application'*/
        /*echo "building version ${NEW_VERSION}"*/
        script {
          gv.buildApp()
        }
        }
        }
    stage("test"){
     /* when {
        expression {
            BRANCH_NAME == 'dev'
        }
      }*/
      steps {
        /*echo 'testing the application'*/
        script {
          gv.testApp()
        }
        }
        }
    stage("deploy"){
      steps {
        echo 'deploying the application'
        /*echo "deploying with ${SERVER_CREDENTIALS}"*/
        echo "deploying version ${params.VERSION}"
        }
        }      
        }}
