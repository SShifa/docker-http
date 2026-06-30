pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Deploy to Docker HTTPD') {
            steps {
                sh '''
                docker rm -f web || true
                docker run -d --name web -p 8081:80 \
                -v $WORKSPACE:/usr/local/apache2/htdocs httpd
                '''
            }
        }
    }
}
