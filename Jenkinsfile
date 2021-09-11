pipeline {
    agent any
    
    stages {
        
        stage('Get Latest Build Number'){
            steps{
                def buildNumber = Jenkins.instance.getItem('test-pipeline-docker').lastSuccessfulBuild.number
            }
        }

        stage('Echo Latest Build Number'){
            steps{
                sh 'echo $buildNumber'
            }
        }
    
    }
}
