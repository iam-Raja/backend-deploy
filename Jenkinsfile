pipeline {
    agent {
        label 'agent-1'
    }
    options {
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
        ansiColor('xterm')
    }
        parameters {
        string(name: 'appVersion', defaultValue: '1.0.0', description: 'app version')
    }
    environment{
        def appversion= ''
        nexusUrl='3.90.81.75:8081' 
    }
    stages{
        stage('backend-deploy'){
            steps{
            sh"""
            echo "Application version: ${params.appVersion}"
            """
            }
        }
    }

    post { 
        always { 
            echo 'I will always say Hello again!'
            deleteDir()
        }
        success { 
            echo 'I will run when pipeline is success'
        }
        failure { 
            echo 'I will run when pipeline is failure'
        }
    }
}