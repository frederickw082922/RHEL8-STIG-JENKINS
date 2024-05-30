pipeline {
    agent any

    stages {
        stage('Git Pull RHEL8-STIG') {
            steps {
                git branch: 'devel', credentialsId: 'a30cb82a-21d9-45ba-8e5b-a8de73c57ef1', url: 'https://github.com/frederickw082922/RHEL8-STIG-JENKINS'
            }
        }
        stage('Run RHEL8-STIG PlayBook') {
            steps {
                ansiblePlaybook disableHostKeyChecking: true, installation: 'Ansible_default_path', inventory: './inventory', playbook: './site.yml', become: true, ansible_become_pass: P@$$word123456789
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}




