pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout your Ansible playbook repository
                git branch: 'main', url: 'https://github.com/Noranxx/ansible-server.git'
            }
        }

        stage('Configure Server') {
            environment {
                ANSIBLE_HOSTS = '/var/jenkins_home/ansible/inve' // Path to your Ansible inventory file
            }
            steps {
                // Execute Ansible playbook
                sh '''
                    ansible-playbook -i /var/jenkins_home/ansible playbook.yml
                '''
            }
        }
    }
}

