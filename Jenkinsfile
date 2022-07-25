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
                        git checkout develop
                        git branch -v
                    """
                }
            }
        }
         stage('Merge') {
             steps {
                script {
                    echo 'Merge changes to main'
                    sshagent (credentials: ['jenkins-local']) {
                        sh """
                            git checkout main
                            git rebase develop
                            
                        """
                    }
                }
             }
         }
    }
}