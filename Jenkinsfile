pipeline {
    agent any 
    stages {
        stage('Stage 1') {
            steps {
                echo 'Hello world!' 
            }
        }
    }
	
	agent any
	stages {
		stage('Fortify Remote Arguments') {
			steps {
				fortifyRemoteArguments transOptions: '-Xmx4G',
				scanOptions: '"-analyzers" "dataflow"'
			}
		}
		stage('Fortify Remote Analysis') {
			steps {
				fortifyRemoteAnalysis remoteAnalysisProjectType: fortifyPython(),
				uploadSSC: [appName: 'vulpy', appVersion: '1.0']
			}
		}
	}
}