pipeline {
	agent any
	stages {
		stage('Fortify Remote Arguments') {
			steps {
				fortifyTranslate addJVMOptions: '', buildID: 'vulpy', excludeList: '', logFile: '', maxHeap: '', projectScanType: fortifyOther(otherIncludesList: '', otherOptions: '')
			}
		}
		stage('Fortify Remote Analysis') {
			steps {
				fortifyRemoteAnalysis remoteAnalysisProjectType: fortifyPython(pythonRequirementsFile: 'requirements.txt', pythonVersion: '3', pythonVirtualEnv: ''), uploadSSC: [appName: 'vulpy', appVersion: '1.0']
			}
		}
	}
}