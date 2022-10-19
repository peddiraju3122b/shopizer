pipeline{
    agent{label 'JDK11'}
    triggers {
        pollSCM '* * * * *'
    }
    stages{
        stage('clone'){
            steps{
                git url: 'https://github.com/peddiraju3122b/shopizer.git',
                    branch: 'develop'
            }
        }
        stage('mvnbuild'){
            steps{
                sh 'mvn package'
            }
        }
    }
}   