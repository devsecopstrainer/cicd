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
        stage('sonar-qube-scan') {
            steps {
withSonarQubeEnv('SonarServer') {
sh """
                        ${SCANNER_HOME}/bin/sonar-scanner \
                        -Dsonar.projectKey=idream-ms \
                        -Dsonar.projectName="idream-ms"
                    """
}
            }
        }
    }
}
