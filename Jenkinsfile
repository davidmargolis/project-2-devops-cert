node {
    checkout scm
    def customImage = docker.build('dmm2168/course-2-project-1:latest')
    docker.withRegistry('', 'docker-hub-credentials') {
        customImage.push()
    }
}
pipeline {
    agent any
    stages {
        stage('Checkout Source') {
            steps {
                checkout scm
            }
        }
        stage('Build Image') {
            def customImage
            steps {
                sh 'docker build -t dmm2168/course-2-project-1:latest .'
            }
        }
        stage('Run Image') {
            steps {
                sh 'docker run --rm dmm2168/course-2-project-1:latest'
            }
        }
        stage('Publish Image') {
            environment {
                DOCKER_CREDS = credentials('docker')
            }
            steps {
                sh 'docker login -u ${DOCKER_CREDS_USR} -p ${DOCKER_CREDS_PSW}'
                sh 'docker push dmm2168/course-2-project-1:latest'
            }
        }
    }
}
