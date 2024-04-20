pipeline {
     agent any
    parameters {
        booleanParam(name:'project', defaultValue: true, description:'this paramater help you to know project name')
        choice(name: 'namespace', choices:['dev','prod','mohamed','stage'], description: '' ) 
    }

    stages {
        stage('check') {
            steps {
                echo "checking your code"
                echo "${params.namespace}"
               
            }
        }

        stage('test') {
            when {
                expression{
                    params.project == true 
                }
            }
            steps {
                echo "testing your app" 
            }
        }
        stage('mohamed') {
            steps {
                echo "your code is deployed right now"
                echo "this BRANCH_NAME  $BRANCH_NAME"
               
            }
        }
        stage('deployment') {  
            steps {
                echo "your code is deployed right now"
                echo "this build number $BUILD_NUMBER"
            }
        }    
    }

}
