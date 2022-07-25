pipeline {
    agent { label 'mestre' }

    stages {
        stage('Build') {
            steps {
                deleteDir()
                checkout scm
                script {
                    echo 'Build Project'
                }
            }
        }
    }
}