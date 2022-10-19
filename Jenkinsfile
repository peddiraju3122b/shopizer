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
                git url: 'git@github.com:peddiraju3122b/shopizer.git',
                    branch: "${params.BRANCH}"
            }
        }
        stage(script){
            steps{
                sh 'git checkout develop'
                sh 'git checkout release'
                sh 'git merge develop --no-ff'
                sh 'git push -u origin release'
            }
        }
    }
}   