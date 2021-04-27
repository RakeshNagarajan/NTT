pipeline{
    agent "k8s-node"
    stages{
        stage("git clone"){
            steps{
                script{
                    sh 'git clone https://github.com/RakeshNagarajan/NTT.git'
                }
            }
        }
        stage("sonarqube scanner"){
            steps{
                script{
                    
                }
            }
        }
        stage("docker build"){
            steps{
                script{
                    sh 'docker build -t rakeshnagarajan/ntt:v1'
                    sh 'docker push rakeshnagarajan/ntt:v1'
                }
            }
        }
        stage("K8s deploy"){
            steps{
                script{
                    sh 'kubectl apply -f NTT/application.yaml'
                }
            }
        }
    }
}