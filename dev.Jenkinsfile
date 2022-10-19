pipeline{
    agent{label 'JDK11'}
    triggers {
        pollSCM ('30 17 * * *')
    }
    stages{
        stage('clone'){
            steps{
                git url: 'https://github.com/peddiraju3122b/shopizer.git',
                    branch: 'release'
            }
        }
        stage('mvnbuild'){
            steps{
                sh 'mvn install'
            }
        }
    }
}   