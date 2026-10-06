pipeline {
    agent any
    environment {
        SCANNER_HOME = tool 'SonarScanner'   // must match the name in Tools config
    }
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
        stage('sonar-qube-scan') {
            steps {
withSonarQubeEnv('SonarServer') {
sh """
    ${SCANNER_HOME}/bin/sonar-scanner \\
    -Dsonar.projectKey=idream-ms \\
    -Dsonar.projectName=idream-ms \\
    -Dsonar.sources=src \\
    -Dsonar.java.binaries=target/classes
"""
}
            }
        }
    }
}
