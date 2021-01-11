pipeline{
    enviroment {
         imagename = "maxpaqzrio/chaperootodo_client"
    registryCredential = 'dockerhub-credentials'
    dockerImage = ''
    }
        agent any
        stages{
            stage('Building image'){
                steps{
                    echo 'building image'
                    dockerImage = docker.build imagename
                }
            }
            stage('Make Files'){
                steps{
                   
                    echo 'made files'
                }
            }
        }
}