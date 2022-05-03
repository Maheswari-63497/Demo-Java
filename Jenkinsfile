
pipeline {
  agent any
 tools {
    maven 'Maven' 
  }
  stages {
	stage('Build') {
	  steps {
		/* echo "Apache Server URL: ${ApacheTomcatURL}" */
		bat 'mvn clean install'
	  }
     }
  stage ('Deploy') {
      steps {
        script {
          /*deploy adapters: [tomcat9(credentialsId: 'tomcat_credential', path: '', url: 'http://dayal-test.letspractice.tk:8081')], contextPath: '/pipeline', onFailure: false, war: 'webapp/target/*.war' */
          
         /* deploy adapters: [tomcat9(credentialsId: 'ApacheTomcatadmin', path: '', url: "${ApacheTomcatURL}")], contextPath: null, war: .war'*/
		
          deploy adapters: [tomcat9(credentialsId: 'ApacheTomcatadmin', path: '', url: 'http://localhost:5000/')], contextPath: null, war: 'target/*.war'

        }
      }
    }
  }
}

