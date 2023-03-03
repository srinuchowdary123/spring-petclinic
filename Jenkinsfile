pipeline {
    agent {label 'git'}
    stages {
        stage ('cd') {
            steps {
                 sh 'cd spring-petclinic'
            }
        }
        stage ('maven') {
            sh 'mvn package'
        }
         stage ('start') {
            steps {
               sh 'java -jar target/*.jar'  
       }
         stage ('start') {
            steps {
               archiveArtifacts artifacts: '**/target/gameoflife.war',
                                 onlyIfSuccessful: true
                junit testResults: '**/surefire-reports/TEST-*.xml'
       }
       
    }
}
    }
