pipeline {
    agent {
        docker {
            image 'node:6-alpine' 
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
    }
}
