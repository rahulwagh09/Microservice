pipeline {
    agent any
 
    stages {
        stage('Deploy to Kubernets') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://E2D5588F090A0AD40C4CACDB003FA97E.gr7.ap-south-1.eks.amazonaws.com']]) {
                sh "kubectl apply -f deployment-service.yml"
            }
            }
        }
        
        stage('Hello') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://E2D5588F090A0AD40C4CACDB003FA97E.gr7.ap-south-1.eks.amazonaws.com']]) {
                sh "kubectl get svc -n webapps"
                }
            }
        }
    }
}
