pipeline {
    agent { label 'agent' }

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