pipeline {
    agent { label 'master' }

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