pipeline {
    agent any
    environment{
      testvariable = "cusotm_variable_defined"
      }
    stages {
        stage('Build') {
            steps {
                sh 'echo "this is build stage"'
		sh "echo jenkins home path -> ${BRANCH}"
		sh "this is custom env variables -> env.testvariable"
            }
        }
        stage('Test') {
	   when{
	      expression{
	            Branch 'main'
		     }
		   }
            steps {
                sh 'echo "this is test stage"'
            }
        }
        stage('Deploy') {
            steps {
                 sh 'echo "this is deploy stage"'
            }
        }
    }
    post{
      always{
           sh 'echo "this is POST BLOCK for testing"'
        }
      }
   }

