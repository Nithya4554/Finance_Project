pipeline {
    agent any
    stages{
        stage('build project'){
            steps{
                git url:'https://github.com/Nithya4554/Finance_Project/', branch: "master"
                sh 'mvn clean package'
              
            }
        }
        stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t nithya45/projectfinance:v1 .'
                    sh 'docker images'
                }
            }
        }
        stage('Deploy') {
            steps {
                sh 'sudo docker run -itd --name My-first-containe21211 -p 8083:8081 nithya45/projectfinance:v1'
                  
                }
            }
    }
}
