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
				sh 'gradlew build'
			}	
		}

		stage('Gradle Run') {
			steps {
				sh 'gradlew run'
			}
		}

		stage('Gradle Check') {
			steps {
				sh 'gradlew check'
			}
		}

		stage('Gradle Clean') {
			steps {
				sh 'gradlew clean'
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
