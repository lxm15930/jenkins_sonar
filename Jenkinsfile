pipeline {
    agent any
	stages {
	stage('code Analysis'){
	  steps {  
	   script {
	           def sonarHome = tool name:'sonarqubeScanner3.2', type:'hudson.plugins.sonar.SonarRunnerInstallation'
				withSonarQubeEnv('sonarqube'){
				bat "${sonarHome}/bin/sonar-scanner"
				 }
				}
				}
	}
	
	
	}
}