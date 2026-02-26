pipeline {
    agent any
    stages {
        stage("Clone code"){
            steps{
                checkout scm
            }
        }
        stage("Verfify files"){
            steps{
                bat 'dir'
            }
        }
        stage("Install dependencies"){
            steps{
                bat 'pip install -r requirements.txt'
            }
        }
        stage("Deploy Application"){
            steps{
                bat '''
                taskkill /F /IM python.exe /T 2>nul
                start /B python app.py
                '''
            }
        }
    }

}