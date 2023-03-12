pipeline {
    agent {
        label 'windows'
    }

    tools {
        maven 'apache-maven-3.8.1'
    }
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/msrinivascharan/mediawiki.git'
            }
        }
        
       
        stage('Docker image mediawiki') {
            steps {
                powershell "docker build -t msrinivascharan/mediawiki:${BUILD_NUMBER} .\mediawiki\."
            }
        }

        stage('Docker publish mediawiki') {
            steps {
                powershell "docker push msrinivascharan/mediawiki:${BUILD_NUMBER}"
            }
        }


        stage('Docker image mariadb') {
            steps {
                powershell "docker build -t msrinivascharan/mariadb:${BUILD_NUMBER} .\mariadb\."
            }
        }

        stage('Docker publish mariadb') {
            steps {
                powershell "docker push msrinivascharan/mariadb:${BUILD_NUMBER}"
            }
        }

       
    }
}