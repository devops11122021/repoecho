properties([pipelineTriggers([githubPush()])])

pipeline {
    agent any
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {
        stage('Example') {
            steps {
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
            }
        }
        stage ('build'){
            steps {
                sh '''
                  echo " this is build stage"
                  pwd
                  echo "$JOB_NAME"
                  sh $WORKSPACE/script.sh
                  echo "newly added"
                   echo "newly added"
                   echo "newly added"
                   echo "newly added"
                '''
            }
        }
        stage ('testing') {
            steps{
                echo "this is testing stage"
            }
        }
        stage ('deploy'){
            steps{
                echo "this is deployement stage"
            }
        }
    }
}
