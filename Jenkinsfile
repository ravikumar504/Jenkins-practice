pipeline {
    agent { label 'Agent-1' }
    stages {
        stage('build') {
            steps {
                script{
                    sh """
                        echo "hello this is build from node"
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
}