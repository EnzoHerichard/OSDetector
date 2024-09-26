pipeline {
    agent any

    stages {
        stage('Get the Code !') {
            steps {
                git branch: 'main', url: 'https://github.com/EnzoHerichard/OSDetector.git'
            }
        }

     /*    stage('Install Python 3.11 and pip') {
            steps {
                sh '''
                sudo apt update
                sudo apt install -y python3.11 python3.11-venv python3.11-dev
                sudo apt install -y python3-pip
                '''
            }
        } */

        stage('Setting permissions and running the script') {
            steps {
                sh 'chmod +x os_detector.py'
            }
        }

        stage('Run Python Script') {
            steps {
                sh 'python3.11 os_detector.py'
            }
        }
    }

    post {
        success {
            echo 'It worked, you Geniuuuus !'
        }
        failure {
            echo 'Ohh god, we are in troubles'
        }
    }
}
