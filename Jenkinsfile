pipeline {
    agent {
        docker { image 'docker:17.05.0-ce-git' }
    }

    stages {
        stage('Build') {
            steps {
                bash 'apk add --no-cache py-pip=9.0.0-r1'
                bash 'pip install docker-compose==1.15.0'
            }
        }
        stage('Test') {
            steps {
               bash 'docker-compose up -d'
               bash 'docker-compose run dockerapp python test.py'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
