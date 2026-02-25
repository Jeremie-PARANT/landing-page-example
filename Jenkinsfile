pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/fredericEducentre/landing-page-example.git'
            }
        }

        stage('Deploy') {
            steps {
                sshagent(credentials: ['alwaysdata-ssh']) {
                    sh '''
                        scp -o StrictHostKeyChecking=no -r * eno@ssh-eno.alwaysdata.net:/home/eno/www/
                    '''
                }
            }
        }
    }
}
