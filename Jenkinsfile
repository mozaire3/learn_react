pipeline {
    agent any
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
    }
    
}
