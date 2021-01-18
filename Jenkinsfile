pipeline{
        agent any
        environment {
            app_version = 'v1'
            rollback = 'false'
            
        }
        stages{
            stage('Build Image'){
                steps{
                    
                    script{
                        if (env.rollback == 'false'){
                            image = docker.build("maxpaqzrio/chaperoo-frontend")
                        }
                    }
                     echo 'image has been built'
                }
            }
            stage('Tag & Push Image'){
                steps{ 
                 
                    script{
                        if (env.rollback == 'false'){
                            docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials'){
                                image.push("${env.app_version}")
                            }
                        }
                           echo 'images tagged and pushed'
                    }
                }
            }
            stage('Deploy App'){
                steps{
                    sh "docker-compose pull && docker-compose up -d"
                }
            }
        }
}
