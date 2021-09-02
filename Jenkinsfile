pipeline{
    agent any
    stages{
        stage("build"){
            step{
            echo "npm building..."
            nodejs('Node-16.8.0'){
                sh "npm install"
            }
          }
        }
        stage("deploy"){
            step{
            echo "npm deploying..."
            nodejs("Node-16.8.0"){
                sh "nohup npm start &"
            }
          }
        }
    }
}