pipeline {
    agent any
    stages {
        
        stage('Start Deploy image') {
            agent {
                kubernetes {
                    
                    defaultContainer 'maven'
                    yamlFile 'jenkinsPod.yml'
                }
            }
            steps {
                git branch: 'main',
                    url: 'https://github.com/stephenatwell/borealis-demo-1.git'
                sh 'ls -lat /usr/local/bin'
                sh 'pwd'
                sh 'armory deploy start -f deploy.yml -c CLIENT_ID -s SECRET'
            }
        }
    }
}
