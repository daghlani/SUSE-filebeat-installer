pipeline {
    agent any

    options {
        disableConcurrentBuilds()
        ansiColor("xterm")
    }

    parameters {
        text  (  name: 'HOSTS', defaultValue: '''[hosts]\n\n\n\n\n\n\n\n[all:vars]\nansible_user=root''' )
    }
    
    stages {
        stage('Installation') {
            steps {
                sh '''
                #!/bin/bash
                echo "$HOSTS" > hosts && cat hosts
                '''
                ansiblePlaybook (
                    inventory: 'hosts',
                    playbook: 'installer.yml',
                    disableHostKeyChecking: true,
                    colorized: true,
                )
            }
        }
    }
}
