pipeline {

    agent {
        label 'jenkins-agent-make'
    }


    stages { 

    
        stage('Push container build job - kaniko') {
            steps {
                withCredentials([file(credentialsId: 'kubeconfig', variable: 'KUBECONFIG')]) {
                    sh 'kubectl config use-context rke2-v3'
                    sh 'kubectl apply -f kaniko.yaml'
                }
            }
        }

        

    }
}
