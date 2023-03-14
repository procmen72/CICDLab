pipeline {
    agent any
    tools {
      nodejs 'NodeJS12LTS'
    }
    stages {
        stage('Build Frontend Web') {
            steps {
                echo 'Building Frontend Angular'
                dir ('Angular6BaseCli/'){
                    bat 'npm install'
                    bat 'npm run build'
                }
            }
        }
    }
    post { 
        always { 
            deleteDir()
        }
        success {
            echo 'I succeeeded!'
        }
        unstable {
            echo 'I am unstable :/'
        }
        failure {
            echo 'I failed :('
        }
        changed {
            echo 'Things were different before...'
        }
    }
}