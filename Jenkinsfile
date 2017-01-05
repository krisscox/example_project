node {
    stage('Checkout') {
        checkout scm
    }

    stage('Provision') {
        sh 'composer install'
        sh 'yarn install'
    }

    stage('Run Tests') {
        sh 'vendor/bin/phpunit'
    }

    stage('PSR-2 Standards') {
        sh 'vendor/bin/phpcs --standard=PSR2 ./src'
    }
}
