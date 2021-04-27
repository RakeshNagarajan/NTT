pipeline{
    agent any
    stages{
        stage("git clone"){
            steps{
                script{
                    //git 'https://github.com/RakeshNagarajan/NTT.git'
                    //sh 'git clone https://github.com/RakeshNagarajan/NTT.git'
                    //sh 'git pull'
                    sh 'ls -lrt'
                }
            }
        }
        stage("sonarqube scanner"){
            steps{
                script{
                    
                    echo "sonar scanner needs to be configured"
                }
            }
        }
        stage("docker build"){
            steps{
                script{
                    sh 'cd $WORKSPACE/NTT; docker build -t rakeshnagarajan/ntt:v1 .'
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
