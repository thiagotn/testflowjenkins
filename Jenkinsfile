pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                deleteDir()
                checkout scm
                script {
                    echo 'Build Project'
                    sh """
                        git branch -v
                    """
                }
            }
        }
    }
}