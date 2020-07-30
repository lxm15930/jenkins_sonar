pipeline {
    agent any
	stages {
	stage('codeAnalysis'){
	  steps {
	   bat """
	     mvn clean verify sonar:sonar \
		 -Dsonar.login=0d01ad741b3f156f7e9ff62257863ed85c6c5d2c \
		-Dsonar.host.url=http://127.0.0.1:9000
		"""
	  }
	}
	}
}