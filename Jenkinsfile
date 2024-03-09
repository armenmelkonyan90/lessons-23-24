pipeline {
    agent any
    triggers {
    GenericTrigger(
        genericVariables: [
            [defaultValue: '', key: 'base', regexpFilter: '', value: '$.ref'],
            ],
     causeString: 'Triggered on $ref',
     token: 'rare',
     tokenCredentialId: '' )
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
