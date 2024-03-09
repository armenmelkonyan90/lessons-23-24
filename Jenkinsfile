pipeline {
    agent any
    triggers {
        GenericTrigger(
            genericVariables: [
                [key: 'targetBranchName', value: '$.body.pull_request.base.ref'],
                [key: 'sourseBranchName', value: '$.body.pull_request.head.ref'],
            ],
            token: ''
        )
    }
    stages {
        stage('Check branch name') {
            steps {
                script {
                    if (env.tagetBranchName != 'dev') {
                        echo "Branch name is not 'dev', proceeding with the merge"
                    } else {
                        error "Merge rejected! Branch name 'dev' is not allowed."
                    }
                }
            }
        }
        stage('Merge to main') {
            steps {
                script {
                        git branch: 'dev', url: 'https://github.com/DavoA/TaskJenkins.git'
                    }
                }
            }
        }
    }
}
