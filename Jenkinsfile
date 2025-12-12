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

		stage('Gradle Check') {
			steps {
				sh './gradlew -Dhttps.proxyHost=proxy1-rech -Dhttps.proxyPort=3128 check -x test'
			}
		}

		stage('Gradle Sonar') {
			steps {
				sh './gradlew sonar -Dsonar.projectKey=SonarQubeProjectKey -Dsonar.projectName=SonarQube -Dsonar.host.url=http://172.17.0.3:9000 -Dsonar.token=sqp_2424e13d0b464b6940a72fb83061fa23746e0293'
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
