
pipeline {
    agent any
    
    stages {
            
        
        stage('Deploy a file'){
	        steps{
	        	kubernetesDeploy configs: 'testremote.yaml', kubeConfig: [path: ''], kubeconfigId: '9d872ae9-c8ea-47b4-88cb-255013d7b1d8', secretName: '', ssh: [sshCredentialsId: '*', sshServer: ''], textCredentials: [certificateAuthorityData: '', clientCertificateData: '', clientKeyData: '', serverUrl: 'https://']
	        }
        }
        
    
    }
}
