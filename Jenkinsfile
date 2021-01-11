pipeline{
        agent any
        stages{
            stage('Make Directory'){
                steps{
                    echo 'made directory'
                }
            }
            stage('Make Files'){
                steps{
                    sh "touch ~/jenkins-tutorial-test/file1 ~/jenkins-tutorial-test/file2"
                    echo 'made files'
                }
            }
        }
}