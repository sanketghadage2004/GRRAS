pipeline {
	agent any 
	
	stages {
	    stage('Checkout') {
	        steps {
			git 'https://github.com/sanketghadage2004/GRRAS.git'			       
		      }}
		stage('Build & compile') {
	           steps {
			  sh '/home/sanket/Documents/devops_sw/apache-maven-3.9.7/bin/mvn install'
	                 }}
		stage('Deployment'){
		   steps {
		sh 'cp target/GRRAS.war /home/sanket/Documents/devops_sw/apache-tomcat-9.0.89/webapps'
			}}	
}}
