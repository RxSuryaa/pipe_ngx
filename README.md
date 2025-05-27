# pipe_ngx


pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                git 'HTTPS URL'
                pwd()
                sh '''docker login -u DocUSername -p DocPass 
                docker pull nginx
                docker rm web --force 
                docker run --name web -d -p 80:80 nginx 
                '''
                echo 'Hello World'
            }
        }
    }
}
