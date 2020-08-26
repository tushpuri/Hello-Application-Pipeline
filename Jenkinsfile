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
		       environment {
			       ANYPOINT_CREDENTIALS = credentials('Anypoint_Studio')
		       }
		       steps {
			       echo 'Deploying only because of code commit in' ${params.env}      
		       }    
	       }  
	}
}
