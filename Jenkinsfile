pipeline {
  
  agent any  { label   'agent'}
  stages {
    stage ( cd )
      steps {
            sh 'cd spring-petclinic'
      }
       stage ( maven)
      steps {
            sh 'mvn package'
      }
       stage ( start)
      steps {
            sh 'java -jar target/*.jar'
      }
         stage ( artifacts)
      steps {

         archive Archive artifacts: '**/target/spring-petclinic.war',

        junit testResults: '**/surefire-reports/TEST-*.xml'
      }
  }    

}
