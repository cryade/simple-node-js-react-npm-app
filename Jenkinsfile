pipeline {
    agent {
        docker {
            image 'node:6-alpine' 
            args '-p 3000:3000' 
        }
    }
     environment {
         HTTPS_PROXY = '16.85.88.60'
         HTTP_PROXY = '16.85.88.60'
         PROXY_ENABLED = 'TRUE'
        CI = 'true'
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
    }
}
