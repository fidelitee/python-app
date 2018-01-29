pipeline {
    agent {
        docker { image 'python:2.7-slim' }
    }
    stages {
        stage('checkout') {
            steps {
              git credentialsId: 'GithubID', url: 'https://github.com/fidelitee/python-app.git'  
            }
        }
    }
}
