pipeline {
    agent any
    environment {
        PROJECT_ID = 'practical-robot-443613-d1'
        CLUSTER_NAME = 'cluster-1'
        REGION = 'us-central1-c'
        CREDENTIALS_JSON = '/root/key.json'
    }
    stages {
        stage('Authenticate with GKE') {
            steps {
                sh '''
                gcloud auth activate-service-account --key-file=$CREDENTIALS_JSON
                gcloud config set project $PROJECT_ID
                gcloud container clusters get-credentials $CLUSTER_NAME --region $REGION
                '''
            }
        }

        stage('Deploy to GKE') {
            steps {
                sh 'kubectl apply -f nginx-deployment.yaml'
            }
        }
    }
}
