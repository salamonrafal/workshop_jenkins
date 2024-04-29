node {
    try {
         stage('[GIT] Run Checkout') {
            checkout scm
        }

        stage('[SSH][vps-f56b0b84] Checking run via SSH without passwd only SSH key') {
            sh "ls -l"
            
            sh """
                ssh jenkins@vps-f56b0b84.vps.ovh.net 'docker -v'
            """
        }
    } catch (Exception e) {
        println('Caught exception: ' + e)

        currentBuild.result = 'FAILED'
    } finally {
        stage('Clean workspace') {
           cleanWs()
        }
    }
}
