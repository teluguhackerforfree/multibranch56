pipeline {
    agent any

    stages {
        stage('master download') {
            steps {
                git 'https://github.com/sunildevops77/maven.git'
            }
        }
        stage('compile') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('build') {
            steps {
                sh 'mvn package'
            }
        }
        stage('deploy') {
            steps {
                deploy adapters: [tomcat9(credentialsId: '28c28ccd-f86d-41cc-9964-dc71be85ae0d', path: '', url: 'http://3.91.217.80:8081/')], contextPath: 'javeedapp', war: '**/*.war'
            }
        }
    }
}
