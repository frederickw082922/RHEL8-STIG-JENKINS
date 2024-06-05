pipeline {
    agent any

    stages {
        stage('Git Clone RHEL8-STIG') {
            steps {
                git branch: 'devel', url: 'https://github.com/frederickw082922/RHEL8-STIG-JENKINS'
            }
        }
        stage('Run RHEL8-STIG PlayBook') {
            steps {
                ansiblePlaybook become: true, becomeUser: 'root', colorized: true, credentialsId: '0f6b1a0c-69d0-43ec-bbfd-d8454f07ad28', disableHostKeyChecking: true, installation: 'Ansible_default_path', inventory: './inventory', playbook: './site.yml', sudoUser: null, vaultTmpPath: ''
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}




