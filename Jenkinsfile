pipeline {
    agent any

    stages {

        stage('build') {
            steps {
              bat '''
                 ./mvnw -DskipTests clean compile
              '''
            }
        }

        stage('test') {
            steps {
              bat '''
                 ./mvnw test
              '''
            }
        }

        stage('deliver') {
            steps {
              echo 'Deploying...'
              bat '''
                 git push https://git.heroku.com/rsvp-service-triston-burns.git HEAD:main -f
              '''
            }
        }

    }
}
