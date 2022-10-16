pipeline{
    agent{label 'JDK11'}
    parameters {
        choice(name: 'BRANCH', choices: ['master', 'develop', 'release'], description: 'all branches')
    }
    triggers {
        cron('30 17 * * *')
    }
    stages{
        stage('clone'){
            steps{
                git url: 'https://github.com/peddiraju3122b/shopizer.git',
                    branch: "${params.BRANCH}"
            }
        }
        stage('mvnbuild'){
            steps{
                sh 'mvn package'
            }
        }
    }
    stages {
        stage(ARTIFACTS) {
            steps{
                archiveArtifacts artifacts: '**/target/*.jar', 
            junit '/**/target/surefire-reports/*.xml'
            }
        }
    }
}

   