pipeline {
    agent {
        label 'Slave_1'
    }
        stages {
            stage('STAGE1'){
                steps{
                    echo 'This is the checkout stage'
                    sh 'sleep 5'
                    //sh 'exit 1'
                }
            }

            stage('STAGE2'){
                steps{
                    echo 'This is the build stage'
                }
            }

             
        }

}
