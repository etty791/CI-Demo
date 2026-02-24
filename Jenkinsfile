pipeline {
    agent any
    environment {
        APP_ENV = "staging"

    }
    options{
        timeout(time: 10, unit: 'SECONDS')
        buildDiscarder(logRotator(numToKeepStr:'5'))
    }
    stages {
        stage('connect to github'){
        steps{
            withCredentials([
    		  usernamePassword(credentialsId: 'demoUser', usernameVariable: 'USER', passwordVariable: 'PASS'),
    		]) {
    		  bat '''
    			echo  Deploying as %USER% %PASS%
    		  '''
    		}
        }
        }
        stage('Hello') {
            steps {
                sleep time: 5, unit: 'SECONDS'
                echo "build number: ${env.BUILD_NUMBER}"
                echo 'Hello World'
                echo "${APP_ENV}"
            }
        }
        stage('learn credentials') {
            steps{
             echo 'learn credentials'
              echo "${APP_ENV}"
            }

        }

        stage('build') {
            steps {
                echo 'The second stage'
                echo 'The second steps'
            }
        }
        stage('Parallel'){
            stage('one'){
                sleep time: 10, unit: 'SECONDS'
    }
             stage('two'){
                sleep time: 10, unit: 'SECONDS'
    }
}
    }





