node {
    try {
         stage('[GIT] Run Checkout') {
            checkout scm
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
