pipeline {
    agent any
    stages {
        stage('git-clone') {
            steps {
                git branch: 'main', url: 'https://github.com/devsecopstrainer/idream-ms.git'
            }
        }
        stage('mvn-build') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
}
