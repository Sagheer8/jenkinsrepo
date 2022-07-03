pipeline {
    agent any
    environment {
        BUILDING_NO = 56

    }
    stages {
        stage("Dev") {
            steps {
                echo "This is development phase"
            }
        }

        stage("Build") {
            steps {
                echo "This is building phase"
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