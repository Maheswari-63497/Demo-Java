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
    stage('SonarQube analysis') {
	   /* steps{
	     withSonarQubeEnv(installationName: 'SonarQubedefault')
     	     {// withSonarQubeEnv(credentialsId: 'f225455e-ea59-40fa-8af7-08176e86507a', installationName: 'My SonarQube Server')		     
		     // You can override the credential to be used
			      bat 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.7.0.1746:sonar'
    	     }
	      }*/
	    
	      environment {
        scannerHome = tool 'SonarQubeScanner'
    	}
    steps {
        withSonarQubeEnv('sonarqube') {
            sh "${scannerHome}/bin/sonar-scanner"
        	}
    	}	
    }
   stage ('Deploy') {
      steps {
        script {
          /*deploy adapters: [tomcat9(credentialsId: 'tomcat_credential', path: '', url: 'http://dayal-test.letspractice.tk:8081')], contextPath: '/pipeline', onFailure: false, war: 'webapp/target/*.war' */
          
          deploy adapters: [tomcat9(credentialsId: 'ApacheTomcatadmin', path: '', url: 'http://localhost:5000/')], contextPath: null, war: 'target/*.war'
        }
      }
    }
  }
}
