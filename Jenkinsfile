pipeline {
	agent any
	
	stages {
		stage('Gradle Build') {
			steps {
				sh 'gradle build'
			}	
		}

		stage('Gradle Run') {
			steps {
				sh 'gradle run'
			}
		}

		stage('Gradle Check') {
			steps {
				sh 'gradle check'
			}
		}

		stage('Gradle Clean') {
			steps {
				sh 'gradle clean'
			}
		}
	}

	post {}
}
