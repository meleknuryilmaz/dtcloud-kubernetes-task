pipeline {
    agent any

    stages {

        stage('Checkout Repository') {
            steps {
                checkout scm
            }
        }

        stage('List Kubernetes Files') {
            steps {
                sh 'ls -la k8s'
            }
        }

        stage('Deploy Manifests') {
            steps {
                sh 'kubectl apply -f k8s/web1-deployment.yaml'
                sh 'kubectl apply -f k8s/web1-service.yaml'

                sh 'kubectl apply -f k8s/web2-deployment.yaml'
                sh 'kubectl apply -f k8s/web2-service.yaml'

                sh 'kubectl apply -f k8s/web3-deployment.yaml'
                sh 'kubectl apply -f k8s/web3-service.yaml'
            }
        }

        stage('Apply Ingress') {
            steps {
                sh 'kubectl apply -f k8s/ingress.yaml'
            }
        }

        stage('Check Pods') {
            steps {
                sh 'kubectl get pods -n cloud-task'
            }
        }

        stage('Check Services') {
            steps {
                sh 'kubectl get services -n cloud-task'
            }
        }

        stage('Pipeline Completed') {
            steps {
                echo 'Pipeline basariyla tamamlandi.'
            }
        }
    }
}
