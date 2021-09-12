def buildVersion = 'UNKNOWN'

pipeline {
    

    agent any


    stages {


        stage('Echo Latest Build Number'){

            steps {
                sh ''' buildNumber=$(curl -X POST -L --user ozkan_poyrazoglu:116174b9818012a2ad096c6dbe62048a92 http://161.35.148.185:8080/job/ci_cd/job/build_pipeline/lastSuccessfulBuild/buildNumber)
                echo $buildNumber
                '''
            }
        }
     
        stage('Edit YAML'){
            steps{
                script {
                  buildVersion = sh(returnStdout: true, script: 'curl -X POST -L --user ozkan_poyrazoglu:116174b9818012a2ad096c6dbe62048a92 http://161.35.148.185:8080/job/ci_cd/job/build_pipeline/lastSuccessfulBuild/buildNumber').trim()
                }
                sh " sed -i \'s/%buildnumber%/${buildVersion}/g\' deploymentsample.yaml "
                sh " sed -i \'s/%buildnumber%/${env.namespace}/g\' deploymentsample.yaml "
                sh ' cat deploymentsample.yaml '

            }
        }


        stage('Apply YAML file in k8s'){
            steps {
                sh ' kubectl apply -f deploymentsample.yaml '
            }
        }




    }

}
