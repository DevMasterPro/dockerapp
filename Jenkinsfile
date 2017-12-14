pipeline {
    agent {
        docker { image 'docker:17.05.0-ce-git' }
    }

    stages {
        stage('Build') {
            steps {
                sh 'apk add --no-cache py-pip=9.0.0-r1'
                sh 'pip install docker-compose==1.15.0'
            }
        }
        stage('Test') {
            steps {
               sh 'docker-compose up -d'
               sh 'docker-compose run dockerapp python test.py'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
