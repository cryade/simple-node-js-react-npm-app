pipeline {
    agent {
        docker {
            image 'node:10.15-alpine'
            args '-p 3000:3000'
        }
    }
    environment { 
        HTTPS_PROXY = 'http://16.85.88.60:8080'
        HTTP_PROXY  = 'http://16.85.88.60:8080'
      
        PROXY_ENABLED = 'TRUE'
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Before Test') {
            steps {
             
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
        stage('Deliver') { 
            steps {
                sh './jenkins/scripts/deliver.sh' 
                input message: 'Finished using the web site? (Click "Proceed" to continue)' 
                sh './jenkins/scripts/kill.sh' 
            }
        }
    }
}
