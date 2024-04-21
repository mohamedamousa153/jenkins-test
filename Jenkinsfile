pipeline {
    agent any

    parameters {
        string(name: 'TARGET', defaultValue: 'World')
    }

    environment {
        GREETING = "Hello"
    }

    stages {
        stage('Greeting') {
            steps {
                script {
                    echo "${env.GREETING}, ${params.TARGET}!"
                }
            }
        }

        stage('Fail Pipeline') {
            steps {
              
                sh 'exit 1'
            }
        }
    }

    post {
        failure {
          
              build job: "replay", wait: true
        }
    }
}
