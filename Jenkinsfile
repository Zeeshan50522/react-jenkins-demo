pipeline{
    agent any

    environment {
        NEXUS_VERSION = "nexus3"
        NEXUS_PROTOCOL = "http"
        NEXUS_URL = "172.17.0.3:8081"
        NEXUS_REPOSITORY = "repository-example"
        NEXUS_CREDENTIAL_ID = "nexus-credentials"
    }
    stages{
        stage("build"){
            steps{
            echo "npm building..."
            nodejs('Node-16.8.0'){
                sh "docker build -t react-frontend"
                sh "docker tag react-frontend http://23.22.224.128:8081/react-frontend"
            }
          }
        }
        stage("Artifacts to Nexus"){
            steps {
                script {
                    docker push react-frontend http://23.22.224.128:8081/react-frontend, 
                    credentialsId: 'nexus-credentials', 
                    groupId: 'com.nbs.nexus', 
                    nexusUrl: '23.22.224.128:8081', 
                    nexusVersion: 'nexus3', 
                    protocol: 'http', 
                    repository: 'react-frontend', 
                    version: '1.0.0'
                }
            }
        }
    }
}