pipeline {
    agent any
    options {
        checkoutToSubdirectory('source')
    }
    tools {
        maven 'MAVEN'
        jdk 'java'
    }
    stages {
        stage ('Build') {
            
            steps {
                dir ('source') {
                    sh '''mvn -Dmaven.test.failure.ignore=true clean install
                          cp -R target/*.war ansible/hello-world.war'''
                }
                
            }
        }
    }
}
