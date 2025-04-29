pipeline {
    agent none
    stages {
        stage('CHECKOUT') {
            agent any

            steps {
                echo "This is a checkout stage"
            }
        }

        stage('BUILD') {
            agent {
                label 'Slave_1'
            } 
            steps {
                echo "This is a build stage"
                sleep 10
            }
        }
    }
    
}
