pipeline {
    agent any
    
    stages {
                
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
