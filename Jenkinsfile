pipeline {
    agent any
    
    stages {
        stage('Setup') {
            steps {
                script {
                    sh 'bash -c "PYTHON=\"/usr/bin/python3\"; $PYTHON -m venv myenv; source myenv/bin/activate"'
                }
            }
        }
        
        stage('Install Dependencies') {
            steps {
                script {
                    sh 'bash -c "source myenv/bin/activate; pip install -r requirements.txt"'
                }
            }
        }
        
        stage('Run Tests') {
            steps {
                script {
                    sh 'bash -c "source myenv/bin/activate; behave"'
                }
            }
        }
    }
}
