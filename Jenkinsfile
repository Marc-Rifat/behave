pipeline {
    agent any
    
    stages {
        stage('Setup') {
            steps {
                script {
                    sh(script: '''
                    #!/bin/bash
                    PYTHON="/usr/bin/python3"
                    $PYTHON -m venv myenv
                    source myenv/bin/activate
                    ''', label: 'Setting up Python environment')
                }
            }
        }
        
        stage('Install Dependencies') {
            steps {
                script {
                    sh(script: '''
                    #!/bin/bash
                    source myenv/bin/activate
                    pip install -r requirements.txt
                    ''', label: 'Installing dependencies')
                }
            }
        }
        
        stage('Run Tests') {
            steps {
                script {
                    sh(script: '''
                    #!/bin/bash
                    source myenv/bin/activate
                    behave
                    ''', label: 'Running
