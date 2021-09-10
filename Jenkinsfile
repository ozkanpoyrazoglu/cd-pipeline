
pipeline {
    agent any
    
    stages {
            
        
        stage('Remote Connection Check'){
	        steps{
	        	def remote = [:]
		        remote.name = 'do_master'
		        remote.host = '188.166.114.130'
		        remote.user = 'root'
		        remote.password = 'BUaw9twzKJ'
		        remote.allowAnyHosts = true
	        }
        }
        

        stage('Put Yaml File to Remote Cluster') {
        	steps{
        		sshPut remote: remote, from: 'testremote.yml', into: '/tmp/'
        	}
        } 
    
    }
}
