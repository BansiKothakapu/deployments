pipeline {
    agent any
    
    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/BansiKothakapu/deployments.git'  // Replace with your repo URL
            }
        }

        
        stage('Deploy Nginx to GKE') {
            steps {
                sh 'kubectl apply -f nginx-deployment.yaml'
            }
        }

        stage('Verify Deployment') {
            steps {
                sh 'kubectl get pods'
                sh 'kubectl get svc'
            }
        }
    }
}
