pipeline {
    agent any

    environment {
        IMAGE_REPO = "ramesh040183"
        IMAGE_ID = "edulab"
        IMAGE_TAG = "latest"
    }

    stages {
        stage('Git_Pull') {
            steps {
                git branch: 'main', url: 'https://github.com/ramesh040183-code/edulab.git'
            }
        }

        stage('Image_Build_Push') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'Dockerhub-creds', 
                    passwordVariable: 'PASSWORD', 
                    usernameVariable: 'USERNAME')]) {

                    bat '''
                    docker build -t %IMAGE_REPO%/%IMAGE_ID%:%IMAGE_TAG% .
                    echo %PASSWORD% | docker login -u --password-stdin
                    docker push %IMAGE_REPO%/%IMAGE_ID%:%IMAGE_TAG%

                    '''
                }
            }
        }

        stage('K8S_Deployment') {
            steps {
                withCredentials([file(
                    credentialsId: 'kubeconfig', 
                    variable: 'kubeconfig')]) {
                
                    bat '''

                    set kubeconfig = %kubeconfig%
                    kubectl config set-context minikube
                    kubeclt get nodes
                    kubectl appyly -f K8S/deployment.yaml
                    kubectl appyly -f K8S/service.yaml

                    '''
                    
                }                
            }
        }        
    }

    post {
        success {
            echo "pipline successful!"
        }
        failure {
            echo "pipline failed! check logs!"
            cleanWs()
        }
    }
}
