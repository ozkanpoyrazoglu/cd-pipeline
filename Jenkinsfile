pipeline {
    agent any

    environment {
        latestBuild = ' '
    }

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
                sh ''' latestbuild=$(curl -X POST -L --user ozkan_poyrazoglu:116174b9818012a2ad096c6dbe62048a92 http://161.35.148.185:8080/job/ci_cd/job/build_pipeline/lastSuccessfulBuild/buildNumber) 
                env.latestBuild = $latestbuild    
                '''
                sh ' sed -i "s/%buildnumber%/$latestbuild/g" deploymentsample.yaml '
                sh ' cat deploymentsample.yaml '
            }
        }


        stage('Apply YAML file in k8s'){
            steps {
                sh ''' pwd '''
            }
        }




    }

}