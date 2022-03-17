
pipeline {
  agent any

  stages {
	stage('Demo Active Choices Parameter') {
	  steps {
		echo "States Selected ${ApacheTomcatURL}"
		echo "Cities Selected ${ApacheTomcatURL}"
	  }
	}
  }
}

pipeline {
  agent any
  tools {
    maven 'Maven' 
  }
  stages {
    stage ('Build') {
       steps {
	    	echo "States Selected ${ApacheTomcatURL}"
		    echo "Cities Selected ${ApacheTomcatURL}"
	   }        
	 /*    steps {
       bat 'mvn clean install'
        script{
          echo "Will deploy to ${ApacheTomcatURL}"
        }
      }*/
    }
   stage ('Deploy') {
      steps {
        script {
        
          /*deploy adapters: [tomcat9(credentialsId: 'tomcat_credential', path: '', url: 'http://dayal-test.letspractice.tk:8081')], contextPath: '/pipeline', onFailure: false, war: 'webapp/target/*.war' */
          
          /*deploy adapters: [tomcat9(credentialsId: 'ApacheTomcatadmin', path: '', url: ${ApacheTomcatURL})], contextPath: null, war: '*.war'*/
        }
      }
    }
  }
}


