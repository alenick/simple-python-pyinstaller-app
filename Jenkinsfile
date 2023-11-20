pipeline {
    agent any 
    stages {
        stage('Build') { 
            agent  any
            steps {
                sh 'python3 -m py_compile sources/add2vals.py sources/calc.py' 
                
            }
        }

	stage('Deliver') {
            agent any 
            steps {
                sh 'python3 -m pyinstaller --onefile sources/add2vals.py'
            }
            post {
                success {
                    archiveArtifacts 'dist/add2vals'
                }
            }
        }
    }
}
