



pipeline {
    agent any
    stages {
        stage ('Test') {
            steps {
                script {
                    //def remote = [:]
                    //remote.name = "root"
                    //remote.host = "47.87.238.108"
                    //remote.allowAnyHosts = true

                    node {
                        def remote = [:]
                        remote.name = "root"
                        remote.host = "47.87.238.108"
                        remote.allowAnyHosts = true
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

        stage ('Message') {
            steps {
                sh 'cd /root | ls -lrt'
                sh "echo 'My name is Sagheer'"
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