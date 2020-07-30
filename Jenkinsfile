pipeline {
    agent any
	stages {
	stage('code Analysis'){
	  steps {
	   withSonarQubeEnv('sonarqube'){
	   bat """
	     mvn clean verify sonar:sonar \
		 -Dsonar.token=0d01ad741b3f156f7e9ff62257863ed85c6c5d2c
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