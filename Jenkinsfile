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
                ansiblePlaybook disableHostKeyChecking: true, installation: 'Ansible_default_path', inventory: './inventory', playbook: './site.yml', become: true, becomeUser: jenkins
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}




