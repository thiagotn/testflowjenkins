pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                deleteDir()
                checkout scm
                script {
                    echo 'Build Project'
                    sshagent (credentials: ['jenkins-local']) {
                        sh """
                            git checkout develop
                            git branch -v
                            echo '\ntext here' >> README.md
                            git status
                            git add README.md
                            git commit -am "teste"
                            git push origin develop
                        """
                    }
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
                            git push origin main
                        """
                    }
                }
             }
         }
    }
}