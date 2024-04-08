pipeline {
    agent {label 'tomcat'}
  stages {
        stage('Checkout') {
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/Bhargavi-lakamsani/hello-world-war.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Push') {
            steps {
                echo 'This is Push Stage'
            }
        }

        stage('Deploy') {
            steps {
                sh 'sudo rsync -av /target/*.war/ /opt/tomcat/webapps/'
            }
        }

    }

}
