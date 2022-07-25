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
        stage('Merge') {
            steps {
                script {
                    echo 'Merge changes to master'
                    sh """
                        git checkout master
                        git rebase develop
                    """
                }
            }
        }
    }
}