pipeline {
    agent any

    stages {
        stage ('Checkout SCM') {

            steps {
                checkout scm
            }
        }
        
        stage ('Compile Stage') {

            steps {
                checkout scm
                withMaven(maven : 'Maven') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'Maven') {
                    sh 'mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'Maven') {
                    sh 'mvn deploy'
                }
            }
        }
    }
}
