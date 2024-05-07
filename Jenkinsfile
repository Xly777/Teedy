pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
        // Building Docker images
        stage('Building image') {
            steps{
                //your command
                sh 'docker build -t teedy .'
            }
        }
        // Uploading Docker images into Docker Hub
        stage('Upload image') {
            steps{
                //your command
                sh 'docker push xerry777/teedy'
            }
        }
        //Running Docker container
        stage('Run containers'){
            steps{
                sh 'docker run -d -p 8084:8080 --name teedy_manual03 teedy'
            }
        }
    }

    post {
        
    }
}
