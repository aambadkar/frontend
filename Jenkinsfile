pipeline {
  agent { label 'workstation'}

 stages {



  stage('Code Quality'){
      steps {
        sh 'sonar-scanner -Dsonar.host.url=http://172.31.41.196:9000 -Dsonar.login=admin -Dsonar.password=admin123 -Dsonar.projectKey=frontend -Dsonar.qualitygate.wait=true'
      }
    }


   stage('Release') {
       when {
       expression { env.TAG_NAME ==~ ".*" }
       }
       steps {
           echo 'CI'
       }
   }
 }

}