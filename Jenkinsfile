pipeline {
    agent any
	stages {
	stage('code Analysis'){
	  steps {  
	   script {
				def sonarHome = tool name:'sonarqubeScanner3.2'
				withSonarQubeEnv('sonarqube'){
				   bat "${sonarHome}/bin/sonar-scanner"
				}
　　		}
		
	  }
	}
	
	stage('Quality Gate'){
			steps{
				script {
					timeout(time:1,unit:'HOURS'){
						waitForQualityGate abortPipeline: true						
						}
　　				}
				}
			}
	}
}