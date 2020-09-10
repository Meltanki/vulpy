pipeline {
	agent any
	stages {
		stage('Fortify Clean') {
			steps {
				fortifyClean addJVMOptions: '', buildID: 'vulpy', logFile: '', maxHeap: ''
			}
		}
		stage('Fortify Scan') {
			steps {
				fortifyScan addJVMOptions: '', addOptions: '', buildID: 'vulpy', customRulepacks: '', logFile: '', maxHeap: '', resultsFile: 'results.fpr'
			}
		}
		stage('Fortify Upload Results') {
			steps {
				fortifyUpload appName: 'vulpy', appVersion: '1.0', failureCriteria: '', filterSet: '', pollingInterval: '', resultsFile: 'results.fpr'
			}
		}
	}
}