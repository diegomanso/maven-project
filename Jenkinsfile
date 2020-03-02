pipeline {
    agent any
    stages{
        stage('Build'){
            steps {
                sh '''
                    PATH=$PATH:/usr/local/Cellar/maven/3.6.3_1/bin
                    mvn --version
                    mvn clean package'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
}