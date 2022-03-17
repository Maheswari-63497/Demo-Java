pipeline {
  agent any
  tools {
    maven 'Maven' 
  }
  stages {
    stage ('Build') {
      steps {
        bat 'mvn clean install'
      }
    }
   stage ('Deploy') {
      steps {
        script {
          /*deploy adapters: [tomcat9(credentialsId: 'tomcat_credential', path: '', url: 'http://dayal-test.letspractice.tk:8081')], contextPath: '/pipeline', onFailure: false, war: 'webapp/target/*.war' */
          
          deploy adapters: [tomcat9(credentialsId: 'admin', path: '', url: 'http://localhost:9090/')], contextPath: null, war: 'target/demo.war'
        }
      }
    }
  }
}
