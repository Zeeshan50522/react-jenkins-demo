pipeline{
    agent any
    stages{
        stage("build"){
            echo "npm building..."
            nodejs('Node-16.8.0'){
                sh "npm install"
            }
        }
        stage("deploy"){
            echo "npm deploying..."
            nodejs("Node-16.8.0"){
                sh "nohup npm start &"
            }
        }
    }
}