pipeline {
    agent any
    options {
        timeout(time: 30, unit: 'MINUTES')
        buildDiscarder(logRotator(numToKeepStr: '20'))
        disableConcurrentBuilds()
        timestamps()
    }
    parameters {
        string(
            name: 'GIT_BRANCH',
            defaultValue: 'master',
            description: 'The branch to be deployed'
        )
    }
    environment {
        GIT_REPO = 'https://github.com/stackexpress-shivam/committest.git'
        GIT_BRANCH = 'master'
        
    }
    stages {

        stage('Update Code') {

            steps {
                timestamps {
                    // Clone the repo
                    timeout(time: 300, unit: 'SECONDS') {
                        //git credentialsId: 'coral-deployer', branch: "$GIT_BRANCH", url: "$GIT_REPO"
                        //sh 'git branch'
                        // sh 'git checkout $branch'
                        sh 'ls -la'
                    }
                }
            }
        }


    }
    post {
        always {
            echo 'Job complete'
        }
        success {
            echo 'Job successful'
        }
        failure {
            echo 'Job failed'            
        }
        unstable {
            echo 'Job unstable'
        }
        changed {
            echo 'Job state changed'
        }
    }

}
