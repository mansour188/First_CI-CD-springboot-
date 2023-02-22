pipeline{
    agent any
    triggers{
        pollSCM '* * * * *'
    }
    stages{
        stage('Build'){
            steps{
                powershell 'gradle assemble --parallel'
            }
        }
        stage('test'){
            steps{
                powershell 'gradle test'
            }

        }
        stage('build docker image'){
            steps{
                powershell 'gradle docker'
            }
        }
        stage('run docker image'){
             steps{
             powershell 'gradle dockerRun'
             }

        }
    }
}
