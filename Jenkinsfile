pipeline {
	agent any
	stages {
		stage('Fortify Clean') {
			steps {
			  sh script: "/var/jenkins_home/Fortify/Fortify_SCA_and_Apps_19.1.0/bin/sourceanalyzer -b vulpy -clean" label: 'fortify clean'
			}
		}
	}
}

