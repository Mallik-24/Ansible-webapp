pipeline {
    agent any

    stages {
        stage('SCM checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Mallik-24/Ansible-webapp.git'
            }
        }
        stage('Run Ansible Playbook') {
            steps {
               ansiblePlaybook credentialsId: 'slave-keys', disableHostKeyChecking: true, installation: 'ansible', inventory: '/etc/ansible/hosts', playbook: 'app.yml', vaultTmpPath: ''
            }
        }
    }
}
