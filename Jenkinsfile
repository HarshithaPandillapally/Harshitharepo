pipeline {
    agent any

    stages {
        stage('Checkout Source') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'GitHub-authentication', variable: 'GITHUB_PAT')]) {
                        git url: 'https://HarshithaPandillapally:${GITHUB_PAT}@github.com/subhayandasguptaPwCGithub/kmc-devops.git', branch: 'feature/harshithap'
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
