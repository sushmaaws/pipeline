pipeline {
    agent any
    tools {
        maven 'Maven 3.5.2'
        jdk 'jdk8'
    }
    stages {
	    
	stage ('checkout') {    
	    steps {
	     git 'https://github.com/sushmaaws/pipeline.git'
	    }
	}	
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }

        stage ('Build') {
            steps {
                sh 'mvn -Dmaven.test.failure.ignore=true install' 
            }
        stage ('Deploy') {
		    steps {
			
			sh 'cp /tmp/maven/sushma-maven/target/sushma-maven-1.0-SNAPSHOT.jar /opt/tomcat/webapps'
                        sh 'echo "finish"'			
			}
        }
    }
}
