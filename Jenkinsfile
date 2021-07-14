@Library('share-file') _
welcomeJob ‘lambdatest’

pipeline { 
    agent {label 'slave-1'}
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') { 
            steps { 
                sh 'touch demo2.sh' 
            }
        }
        stage('Test'){
            steps {
                sh 'echo "echo "hello world new"" > demo2.sh'
                 
            }
        }
        stage('Deploy') {
	input{
    	message "Do you want to proceed for production deployment?"
  	}
            steps {
		echo "Deploying and running the production"
                sh 'chmod +x demo2.sh'
                sh './demo2.sh'
            }
        }
    }
}
