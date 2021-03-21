pipeline {
    agent none
	options {
	  checkoutToSubdirectory('gulabi')
	}
    stages {
         
     
        stage('dockerfile'){            
		agent {
			dockerfile {
				customWorkspace '/var/lib/jenkins/workspace/pl_docfile_cws/gulabi/gulabi'
			}
		}
            steps{
                sh 'cat /etc/lsb-release'
            }
        }
    }
}
