
pipeline {
    agent any
    
    stages {
            
        
        stage('Deploy a file'){
	        steps{
	        kubernetesDeploy configs: 'testremote.yaml', kubeConfig: [path: ''], kubeconfigId: 'testkubeconfig', secretName: '', ssh: [sshCredentialsId: '*', sshServer: ''], textCredentials: [certificateAuthorityData: '', clientCertificateData: '', clientKeyData: '', serverUrl: 'https://']
	        }
        }
        
    
    }
}
