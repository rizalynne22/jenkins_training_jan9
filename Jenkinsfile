pipeline {
    agent any

    stages {
        stage('Checkout'){
            steps {
              git url: 'https://github.com/rizalynne22/jenkins_training_jan9.git',
                  branch: 'main'
            }
        }
        stage('Run Tests') {
            steps {
              sh 'npm install'
              sh 'CI=true npm test'
           }
        }
        stage('Build Webpack') {
            steps {
                sh 'npm run build'
            }
        }
        stage('Archive') {
            steps {
              sh 'tar -czf build.tar.gz build'
              archiveArtifacts 'build.tar.gz'
            }
        }
    }
}
