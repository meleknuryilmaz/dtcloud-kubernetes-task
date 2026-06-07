pipeline {
    agent any

    stages {
        stage('Checkout Repository') {
            steps {
                echo 'GitHub repository Jenkins tarafindan alindi.'
            }
        }

        stage('List Kubernetes Files') {
            steps {
                bat 'dir k8s'
            }
        }

        stage('Deploy Manifests') {
            steps {
                echo 'kubectl apply -f k8s/ komutu ile manifestler uygulanacak.'
            }
        }

        stage('Apply Ingress') {
            steps {
                echo 'Ingress kaynaklari uygulanacak.'
            }
        }

        stage('Check Pods') {
            steps {
                echo 'kubectl get pods -n cloud-task ile pod durumlari kontrol edilecek.'
            }
        }

        stage('Check Services') {
            steps {
                echo 'kubectl get services -n cloud-task ile service durumlari kontrol edilecek.'
            }
        }

        stage('Pipeline Completed') {
            steps {
                echo 'Pipeline basariyla tamamlandi.'
            }
        }
    }
}