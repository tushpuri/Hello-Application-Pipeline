pipeline {  
	agent any
	properties([parameters([string(defaultValue: 'Sandbox', description: '', name: 'env', trim: false)])])
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
			       echo 'Deploying only because of code commit in ${env}'
			       echo '${ANYPOINT_CREDENTIALS_USR}'
			       bat 'mvn package deploy -DmuleDeploy -Danypoint.environment=${parameters.env} -Danypoint.username=tusharpuri002 -Danypoint.password=TushP0101 -Danypoint.workers=1 -Danypoint.workersType=MICRO -Danypoint.applicationName=Hello-Application-2 -Danypoint.muleVersion=4.3.0 -DobjectStoreV2=true'
		       }    
	       }  
	}
}
