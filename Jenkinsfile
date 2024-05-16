pipeline {
    agent any

    stages {
        stage('Git Pull RHEL8-STIG') {
            steps {
                git branch: 'devel', credentialsId: 'a30cb82a-21d9-45ba-8e5b-a8de73c57ef1', url: 'https://github.com/frederickw082922/RHEL8-STIG-JENKINS'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}




