pipeline {

    agent {
        label 'jenkins-agent-make'
    }


    stages { 

    
        stage('Push container build job - kaniko') {
            steps {
                withCredentials([file(credentialsId: 'kubeconfig', variable: 'KUBECONFIG')]) {
                    sh 'kubectl config use-context my-context'
                    sh 'kubectl apply -f kaniko.yaml'
                }
            }
        }

        

    }
}
