pipeline {
    agent { label 'Agent-1' }
    environment {
        project = 'Expense'
    }
    options {
        disableConcurrentBuilds()
        timeout(time: 5, unit: 'SECONDS')
    }
    stages {
        stage('build') {
            steps {
                script{
                    sh """
                        echo "hello this is build from node"
                        echo "project: $project"
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
            steps {
                script{
                    sh """
                        echo "hello this is deploy"
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