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
}
