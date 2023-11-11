pipeline {
	agent any
	
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/kunal/Documents/Devops_software/tar/apache-maven-3.9.5/bin/mvn install'
	                 }}
		stage('Deployment'){
		    steps {
			
			sh 'cp target/project4.war /home/kunal/Documents/Devops_software/tar/apache-tomcat-9.0.82/webapps'
			}}
		stage('slack notification'){
		    steps {
			
			slackSend baseUrl: 'https://hooks.slack.com/services/', channel: '#grras-test', color: 'good', message: 'welcome to grras channel', teamDomain: 'devops', tokenCredentialId: 'jenkins-pipeline-new'
			}}
	}}
