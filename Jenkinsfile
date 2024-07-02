pipeline {
	agent any
	
	parameters {
		choice(name: 'ENVIRONMENT', choices: ['QA','UAT'], description: 'Pick Environment value')
	}
	stages {
	    stage('Checkout') {
	        steps {
			git 'https://github.com/sanketghadage2004/GRRAS.git'			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/sanket/Documents/devops_sw/apache-maven-3.9.7/bin/mvn install'
	                 }}
		stage('Deployment'){
		    steps {
			script {
			 if ( env.ENVIRONMENT == 'QA' ){
        	sh 'cp target/GRRAS.war /home/sanket/Documents/devops_sw/apache-tomcat-9.0.89/webapps'
        	echo "deployment has been done on QA!"
			 }
			elif ( env.ENVIRONMENT == 'UAT' ){
    		sh 'cp target/GRRAS.war /home/sanket/Documents/devops_sw/apache-tomcat-9.0.89/webapps'
    		echo "deployment has been done on UAT!"
			}
			echo "deployment has been done!"
			fi
			
			}}}	
}}
