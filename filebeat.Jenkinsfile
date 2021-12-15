pipeline {
    agent any

    options {
        disableConcurrentBuilds()
        ansiColor("xterm")
    }

    parameters {
        text  (  name: 'HOSTS', defaultValue: '''[hosts]\n\n\n\n''' )
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
