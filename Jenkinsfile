node('dqa') {
        stage('git') {
        git 'https://github.com/wakaleo/game-of-life.git'

        stage('build') {
            sh 'mvn clean package'
        }
        stage('testresults'){
            junit 'gameoflife-web/target/surefire-reports/*.xml'
        }
    }
        stage('archieveartifacts') {
            archiveArtifacts artifacts: 'gameoflife-web/target/*.war', followSymlinks: false
        }
}