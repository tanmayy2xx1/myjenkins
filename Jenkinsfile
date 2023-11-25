pipeline {
    agent any
    stages {
        stage ('build docker image') {
            steps {
                sh '/usr/bin/docker image build -t tanmay8180/jenkinsdemo .'
            }
        }
        stage ('docker login') {
            steps {
                sh 'echo dckr_pat_kdCg8GisGtHc7gyoaCguzj2H6iE | /usr/bin/docker login -u tanmay8180 --password-stdin'
            }
        }
        stage ('push docker image') {
            steps {
                sh '/usr/bin/docker image push tanmay8180/jenkinsdemo'
            }
        }
        stage ('reload docker service') {
            steps {
                sh '/usr/bin/docker service update --image tanmay8180/jenkinsdemo --force myservice'
            }
        }

    }
}
