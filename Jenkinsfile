pipeline {
    agent any
    def buildNumber = Jenkins.instance.getItem('test-pipeline-docker').lastSuccessfulBuild.number
    stages {
        


        stage('Echo Latest Build Number'){
            steps{
                sh 'echo $buildNumber'
            }
        }
    
    }
}
