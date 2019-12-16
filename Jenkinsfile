pipeline {
	agent any
    stages {
	    
	stage ('checkout') {    
	    steps {
	     git 'https://github.com/sushmaaws/pipeline.git'
	    }
	}	

        stage ('Build') {
            steps {
		   sh "${MAVEN_HOME}/bin/mvn clean package -Dmaven.test.skip=true"
            }
	}
        stage ('Deploy') {
		    steps {
			
			sh 'cp /tmp/maven/sushma-maven/target/sushma-maven-1.0-SNAPSHOT.jar /opt/tomcat/webapps'    
			}
        }
    }
}
