pipeline{
    environment {
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
             stage('Deploy Image') {
                steps{
                    script {
                        docker.withRegistry( '', registryCredential ) {
                        dockerImage.push("$BUILD_NUMBER")
                        dockerImage.push('latest')

          }
        }
      }
    }
            stage('Make Files'){
                steps{
                   
                    echo 'made files'
                }
            }
        }
}