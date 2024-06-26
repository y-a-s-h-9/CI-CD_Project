 pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/y-a-s-h-9/CI-CD_Project.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    dockerImage = docker.build("intel/intel-optimized-clickhouse:latest")
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    dockerImage.inside {
                        sh 'npm test'
                    }
                }
            }
        }

        stage('Push') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'yashashvib9/Yashashvi@56') {
                        dockerImage.push("${env.BUILD_ID}")
                        dockerImage.push("latest")
                    }
                }
            }
        }

        stage('Deploy to Staging') {
            steps {
                script {
                    kubectl apply -f deployment.yaml
                    kubectl apply -f service.yaml
                }
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}
