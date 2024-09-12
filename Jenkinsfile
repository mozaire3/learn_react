pipeline {
    agent {
        docker { image 'node:20.17.0-alpine3.20' }
    }
    tools {
        nodejs 'Node'
    }
    stages {
        stage('Git checkout') {
            steps {
                git url:"https://github.com/mozaire3/learn_react.git",branch:"main"
            }
        }
        stage('Install npm') {
            steps {
                sh"npm install"
            }
        }
        stage('Build node') {
            steps {
                sh"npm run build"
            }
        }
        stage('docker') {
            steps {
                sh"docker build --tag helloworld:$BUILD_NUMBER ."
                sh"docker run --name helloworld -p 5173:5173 helloworld:$BUILD_NUMBER"

            }
        }
    }
    
}



