pipeline {
    agent any
	stages {
	stage('codeAnalysis'){
	  steps {
	   bat """
	     mvn clean verify sonar:sonar
		"""
	  }
	}
	}
}