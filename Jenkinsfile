pipeline {
    agent any
	stages {
	stage('code Analysis'){
	  steps {
	   withSonarQubeEnv('sonarqube'){
	   bat """
	     mvn clean verify sonar:sonar \
		 -Dsonar.login=admin1 \
		 -Dsonar.password=admin1
		"""
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