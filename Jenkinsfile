
def gv

pipeline {
    agent any
    environment {
        BUILDING_NO = 56

    }
    stages {
        stage("groovyinit") {
            steps {
                script {

                    gv = load "script.groovy"

                }
            }
        }



        stage("Dev") {
            steps {
                echo "This is development phase"
                gv.Dev()
            }
        }

        stage("Build") {
            steps {
                echo "This is building phase"
                echo "Building number is ${BUILDING_NO}. Therefore it will not deploy"
            }
        }

        stage("Deployment") {
            when {
                expression {
                    BUILDING_NO == 43

                }
                
            }
            steps {
                echo "This is deployment phase"
            }
        }

        
    }

    post {
        success{
            echo "Hello everything is successfull"
            echo "check"
        }
    }
}