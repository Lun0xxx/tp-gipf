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

	post {
		always {
			echo 'Pipeline terminée'
		}
		
		success {
			echo 'Terminée avec succès'
		}
		
		failure {
			echo 'Terminée avec un/des erreur(s)'
		}
	}
}
