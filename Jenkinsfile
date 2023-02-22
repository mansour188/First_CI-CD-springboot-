pipeline{
    agent any
    triggers{
        pollSCM '* * * * *'
    }
    stages{
        stage('Build'){
            steps{
                 gradle assemble
            }
        }
        stage('test'){
            steps{
                 gradle test
            }

        }
        stage('build docker image'){
            steps{
                powershell gradle docker
            }
        }
        stage('run docker image'){
             steps{
             powershell gradle dockerRun
             }

        }
    }
}