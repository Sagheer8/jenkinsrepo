



pipeline{
    agent any
    stages{
        stage('Testing stage') {
            steps {
                script {
                    withCredentials( [usernamePassword( credentialsId: 'linux-vps', usernameVariable: 'root', passwordVariable: 'Sagheer')]){
                        sh echo "Heelo"
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