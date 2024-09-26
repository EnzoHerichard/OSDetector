pipeline {
    agent any

    stages {
        stage('Get the Code !') {
            steps {
                git branch: 'main', url: 'https://github.com/EnzoHerichard/OSDetector.git'
            }
        }

        stage('Install Python 3.11 and pip') {
            steps {
                sh '''
                apt update
                apt install -y software-properties-common
                add-apt-repository ppa:deadsnakes/ppa
                apt update
                apt install -y python3.11 python3.11-venv python3-pip
                '''
            }
        }

        stage('Setting permissions and running the script') {
            steps {
                sh 'chmod +x os_detector.py'
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
