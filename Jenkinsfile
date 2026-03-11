node {

    stage("Checkout") {
        checkout scm
    }

    stage("Build") {
        docker.image('php:8.2-cli').inside('-u root') {
            sh 'php -v'
            sh 'composer install'
        }
    }

    stage("Test") {
        docker.image('ubuntu').inside('-u root') {
            sh 'echo "Running Test"'
        }
    }

}