pipeline {
    agent any 
	stages {
		stage('Fortify Clean') {
			steps {
				fortifyClean buildID: 'vulpy',
				logFile: 'vulpyFortify.log'
			}
		}
		stage('Fortify Translate') {
			steps {
				fortifyTranslate buildID: 'vulpy',
				logFile: 'vulpy-translate.log',
				projectScanType: fortifyOther()	
			}
		}
		stage('Remote Fortify Scan Upload to SSC') {
			steps {
				fortifyRemoteScan buildID: 'vulpy',
				uploadSSC: [appName: 'vulpy', appVersion: '1']
			}
		}
	}
}