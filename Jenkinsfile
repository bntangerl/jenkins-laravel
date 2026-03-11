node {

    stage("Checkout") {
        checkout scm
    }

    stage("Build") {
        docker.image('composer:2.7-php8.2').inside('-u root') {
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