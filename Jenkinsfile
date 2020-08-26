pipeline {  
	agent any  
	stages {
		stage('Build Application') {
	        	steps {
	                	bat 'mvn clean install'
			}
		}
	        stage('Test') {
	               steps {
	                  	echo 'Test Appplication...' 
        		  	bat 'mvn clean test'      
        		}   
		}
               stage('Deploy CloudHub') {
		       steps {
			       echo 'Deploying only because of code commit...'      
                               bat 'mvn package deploy -DmuleDeploy'
		       }    
	       }  
	}
}
