pipeline {
	agent any
	
	stages {
		stage('Fetch Git') {
			steps {
				git branch: 'master', url: 'https://github.com/Lun0xxx/tp-gipf.git'
			}
		}

		stage('Gradle Build') {
			steps {
				sh './gradlew -Dhttps.proxyHost=proxy1-rech -Dhttps.proxyPort=3128 build'
			}	
		}

		stage('Gradle Run') {
			steps {
				sh './gradlew -Dhttps.proxyHost=proxy1-rech -Dhttps.proxyPort=3128 run'
			}
		}

		stage('Gradle Check') {
			steps {
				sh './gradlew -Dhttps.proxyHost=proxy1-rech -Dhttps.proxyPort=3128 check'
			}
		}

		stage('Gradle Clean') {
			steps {
				sh './gradlew -Dhttps.proxyHost=proxy1-rech -Dhttps.proxyPort=3128 clean'
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
