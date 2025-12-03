pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                docker build -t my-app .
            }
        }
        stage('Test') {
            steps {
                docker run -it my-app npm run test
            }
        }
        stage('Deploy') {
            steps {
                kubectl apply -f deployment.yaml
            }
        }
    }
}
