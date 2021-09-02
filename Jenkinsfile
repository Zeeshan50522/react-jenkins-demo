pipeline{
    agent any
    stages{
        stage("build"){
            steps{
            echo "npm building..."
            nodejs('Node-16.8.0'){
                sh "npm install"
            }
          }
        }
        stage("deploy"){
            steps{
            echo "npm deploying..."
            nodejs("Node-16.8.0"){
                sh "npm start"
            }
          }
        }
    }
}