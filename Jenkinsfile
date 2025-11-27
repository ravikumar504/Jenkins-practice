pipeline {
    agent { label 'Agent-1' }
    environment {
        project = 'Expense'
    }
    options {
        disableConcurrentBuilds()
        timeout(time: 60, unit: 'SECONDS')
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {
        stage('build') {
            steps {
                script{
                    sh """
                        echo "hello this is build from node"
                        echo "project: $project"
                        echo "Hello ${params.PERSON}"

                        echo "Biography: ${params.BIOGRAPHY}"

                        

                        echo "Choice: ${params.CHOICE}"

                        echo "Password: ${params.PASSWORD}"
                    """
                }
            }
        }
        stage('test') {
            steps {
                script{
                    sh """
                        echo "hello this is test node"
                    """
                }
            }
        }
        stage('deploy') {
            input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
            }
            steps {
                script{
                    sh """
                        echo "hello this is deploy from node"
                    """
                }
            }
        }
        
        
    }
    post {
        always {
            echo "i will always say hello"
        }
        failure {
            echo "i will always say hello"
        }
        success {
            echo "i will always say hello"
        }
    }
}