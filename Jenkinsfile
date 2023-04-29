pipeline {
    agent any

    stages {
        stage('SCM') {
            steps {
                git branch: 'main', url: 'https://github.com/gourav631/Ecommerce_website'
            }
        }
        stage('Build') {
            steps {
                powershell '''docker rm -f ecom-container
                docker build . -t ecom
                docker run -d --name ecom-container -p 8000:80 ecom'''
            }
        }
    }
}
