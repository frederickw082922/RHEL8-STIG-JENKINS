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
                ansiblePlaybook become: true, becomeUser: 'root', colorized: true, credentialsId: 'e9d33be1-a884-4fe2-bdb9-74985383e762', disableHostKeyChecking: true, installation: 'Ansible_default_path', inventory: './inventory', playbook: './site.yml', sudoUser: null, vaultTmpPath: ''
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}




