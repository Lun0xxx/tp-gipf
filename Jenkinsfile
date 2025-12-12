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
				sh './gradlew -Dhttps.proxyHost=proxy1-rech -Dhttps.proxyPort=3128 build -x test'
			}	
		}

		stage('Gradle Run') {
			steps {
				sh './gradlew -Dhttps.proxyHost=proxy1-rech -Dhttps.proxyPort=3128 run -x test'
			}
		}

		stage('Gradle Check') {
			steps {
				sh './gradlew -Dhttps.proxyHost=proxy1-rech -Dhttps.proxyPort=3128 check -x test'
			}
		}

		stage('Gradle Clean') {
			steps {
				sh './gradlew -Dhttps.proxyHost=proxy1-rech -Dhttps.proxyPort=3128 clean -x test'
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
