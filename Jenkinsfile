#!groovy

pipeline {
    agent any
    stages {
        stage('Policy-Code Analysis') {
            steps {
                bat "npm install -g apigeelint"
                bat "apigeelint -s Login-API/apiproxy/ -f codeframe.js"
            }
        }
        stage('Deploy to Production') {
            steps {
                 //deploy using maven plugin
                 
                 // deploy only proxy and deploy both proxy and config based on edge.js update
                //bat "sh && sh deploy.sh"
                bat "mvn -f Login-API/pom.xml install -Pprod -Dusername=hari.80366@gmail.com -Dpassword=Nihira@123 -Dapigee.config.options=update"
            }
        }
    }
}