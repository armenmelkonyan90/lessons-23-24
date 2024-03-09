pipeline {
    agent any
    triggers {
    GenericTrigger(
        genericVariables: [
            [defaultValue: '', key: 'base', regexpFilter: '', value: '$.ref'],
            ],
     causeString: 'Triggered on $ref',
     token: 'test',
     tokenCredentialId: '' )
  }

    stages {
        stage('Check branch name') {
            steps {
                    echo '$base'
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
