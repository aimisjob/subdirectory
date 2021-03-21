pipeline {
    agent none
    stages {
        stage('Checkout') {
            agent any
            steps {                
                checkout([$class: 'GitSCM', 
				branches: [[name: "origin/master"]], 
				userRemoteConfigs: [[
                url: 'https://github.com/aimisjob/subdirectory.git']],
				extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'checkout-directory']]
				])
            }
        }
        stage('dockerfile'){            
            agent {
                dockerfile {
                    customWorkspace '/var/lib/jenkins/workspace/pl_docfile_cws/checkout-directory'
                } 
            }            
            steps{
                sh 'cat /etc/lsb-release'
            }
        }
    }
}
