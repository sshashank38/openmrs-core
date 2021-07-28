
node('master') {

    stage('scm') {
        git 'https://github.com/sshashank38/openmrs-core.git'
    }

    stage('build') {
        sh 'mvn clean package'
    }

    stage('postbuild'){
        junit '**/TEST-*.xml'
        archiveArtifacts artifacts: '**/*.war', followSymlinks: false
    }
}