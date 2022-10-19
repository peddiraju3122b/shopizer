pipeline{
    agent{label 'JDK11'}
    triggers {
        cron('30 17 * * *')
    }
    stages{
        stage('clone'){
            steps{
                git url: 'git@github.com:peddiraju3122b/shopizer.git',
                    branch: 'daybuild'
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