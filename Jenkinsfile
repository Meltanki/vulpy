pipeline {
	agent any
	stages {
		stage('Fortify Remote Arguments') {
			steps {
				fortifyRemoteArguments scanOptions: '', transOptions: ''
			}
		}
		stage('Fortify Remote Analysis') {
			steps {
				fortifyRemoteAnalysis remoteAnalysisProjectType: fortifyPython(pythonRequirementsFile: '', pythonVersion: '3', pythonVirtualEnv: ''), uploadSSC: [appName: 'vulpy', appVersion: '1.0']
			}
		}
	}
}