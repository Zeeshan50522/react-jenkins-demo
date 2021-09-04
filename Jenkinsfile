pipeline{
    agent any

    stages{
        stage("build"){
            steps{
            echo "npm building..."
            nodejs('Node-16.8.0'){
                sh "docker build -t react-fronte"
                sh "docker tag react-frontend react-frontend"
            }
          }
        }
        stage("Artifacts to Nexus"){
            steps {
                script {
                    docker push react-frontend, 
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