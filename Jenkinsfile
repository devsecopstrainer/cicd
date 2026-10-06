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
                sh """
   mvn clean verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar \
  -Dsonar.projectKey=idream-ms \
  -Dsonar.projectName='idream-ms' \
  -Dsonar.host.url=http://13.204.81.113:9000 \
  -Dsonar.token=sqp_2b1d64c29246e05f45a017335048fdfc67de8c08
                """
            }
        }
    }
}
