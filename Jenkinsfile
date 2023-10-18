pipeline {
    agent any

    stages {
        stage('Checkout Source') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'PAT-H', variable: 'GITHUB_PAT')]) {
                        git url: 'https://HarshithaPandillapally:${GITHUB_PAT}@github.com/HarshithaPandillapally/Harshitharepo.git', branch: 'main'
                    }
                }
            }
        }

        stage('Deploy App') {
            steps {
                script {
                    kubernetesDeploy(configs: "nginx.yaml", kubeconfigId: "master-node-1")
                }
            }
        }
    }
}
