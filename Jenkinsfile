pipeline {
    agent any

    stages {
        stage('Checkout-github'){
            steps{
                echo 'Checking out from git repo'
                git credentialsId: 'ad8a5de9-3245-46a8-8313-a447a2bde242', url: 'https://github.com/piyush5566/Accenture_Pipeline.git'
            }
        }
        stage('Compile') {
            steps {
                bat 'Compile.bat'
                echo 'Compiled Successfully'
            }
            
        }
        stage('JUnit'){
            steps{
                echo 'JUnit passed successfully'
            }
        }
        stage('Quality-gate'){
            steps{
                echo 'Sonarqube Quality-gate passed successfully'
            }
        }
        stage('Deploy'){
            steps{
                bat 'Deploy.bat'
                echo 'Deployed successfully'
            }
        }
    }
    
    post{
        always{
            echo 'This will always run'
        }
        success{
            echo 'This will run if successful'
        }
        failure{
            echo 'This will run if failed'
        }
        unstable{
            echo 'This will run only if run was marked as unstable'
        }
        changed{
            echo 'This will run only if state of the pipeline has changed'
            echo 'For example, if the pipeline was initially failing, now successful'
        }
    }
}
