pipeline {
 agent any  { label   'agent'}
 stages {

     stage ( cd )
             steps {
            sh 'cd spring-petclinic'
      }
       stage ( maven )
             steps {
            sh 'mvn package'
      }
       stage ( start )
             steps {
           sh 'java -jar target/*.jar'
      }
       stage ( postbuild )
             steps {
           archiveArtifacts artifacts: '**/target/gameoflife.war',
                                 onlyIfSuccessful: true
                junit testResults: '**/surefire-reports/TEST-*.xml'
      }



    }
  
}
