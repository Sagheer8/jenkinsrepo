



pipeline {
    agent any
    stages {
        stage ('Test') {
            steps {
                script {
                    def remote = [:]
                    remote.name = "root"
                    remote.host = "149.57.169.87"
                    remote.allowAnyHosts = true

                    node {
                        withCredentials([sshUserPrivateKey(credentialsId: 'jenkins-id', keyFileVariable: 'identity', passphraseVariable: '', usernameVariable: 'root')]) {
                            remote.user = root
                            remote.identityFile = identity
                            stage("Connection of server") {
                                sshCommand remote: remote, command: "cd /root/bashscripts; ls -lrt"
                            }
                        }
                    }
                }
            }
        }
    }
}



'''
def remote = [:]
remote.name = "root"
remote.host = "149.57.169.87"
remote.allowAnyHosts = true

node {
    withCredentials([sshUserPrivateKey(credentialsId: 'jenkins-id', keyFileVariable: 'identity', passphraseVariable: '', usernameVariable: 'root')]) {
        remote.user = root
        remote.identityFile = identity
        stage("SSH Steps Rocks!") {
            sshCommand remote: remote, command: "cd /root/bashscripts; ls -lrt"
        }
    }
}

'''