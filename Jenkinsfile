pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Integrating new changes"'
            }
        }
        stage('Deploy to test environment') {
            when {
                branch 'development'
            }
            steps {
                sh 'echo "Publishing to staging environment."'
            }
        }
        stage('Pushes a Docker image with the code to Dockerhub') {
            when {
                branch 'main'
            }
            steps {
                sh 'echo "Publishing to production environment and pushing code to dockerhub."'
                sh 'docker login -u nyamburamuhia@gmail.com -p 201288muhia'
                sh 'docker build -t nyamburamuhia/gitflow-uppgift:1.0.0 .'
                sh 'docker push nyamburamuhia/gitflow-uppgift:1.0.0'
            }
        }
    }
}
