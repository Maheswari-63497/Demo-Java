pipeline {
  agent any
  tools {
    maven 'Maven' 
  }
  stages {
    stage ('Build') {
      steps {
        bat 'mvn clean package'
      }
    }
   stage ('Deploy') {
      steps {
        script {
          /*deploy adapters: [tomcat9(credentialsId: 'tomcat_credential', path: '', url: 'http://dayal-test.letspractice.tk:8081')], contextPath: '/pipeline', onFailure: false, war: 'webapp/target/*.war' */
          
          deploy adapters: [tomcat9(credentialsId: 'tomcatadmin', path: '', url: 'http://localhost:5050/')], contextPath: null, war: 'target/web-app.war'
        }
      }
    }
  }
}
