pipeline {
    agent any

    stages {
        stage('Checkout Source') {
            steps {
                script {
                    git credentialsId: 'my-github',
                        url: 'https://github.com/HarshithaPandillapally/Harshitharepo.git',
                        branch: 'main'
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
