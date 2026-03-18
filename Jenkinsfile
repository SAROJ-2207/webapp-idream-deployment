pipeline{
 tools{
        jdk 'JAVA_HOME'
        maven 'M2_HOME'
    }
     agent any
	  
	  stages{
	  
	  stage("checkout"){
	   steps{
	   git 'https://github.com/nishankainfo/webapp.git'
	   }
	                  }
	
	   stage("compile"){
	    steps{
		 sh 'mvn compile'
		}
		}
       stage("test"){
	    steps{
		 sh 'mvn test'
		}
		}
       stage("package"){
	    steps{
		 sh 'mvn clean package'
                 sh "mv target/*.war target/myweb.war"

		}
		}
   stage("deploy"){
	   steps{
			echo "deploy success"
        
		}
		  
	  }
stage(backup)
		  {
  steps{
      sh 'mvn deploy'
	  //nexusArtifactUploader artifacts: [[artifactId: 'idream-it-solutions', classifier: '', file: 'target/myweb.war', type: '.war']], credentialsId: 'nexus', groupId: 'com.idream.webapp', nexusUrl: '13.204.79.196:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'repoR', version: '1.1'
  }
	
}

	}
	}
