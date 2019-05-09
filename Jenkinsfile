pipeline {
  agent any
  environment {
    ANYPOINT_APP_NAME = 'mule4jenkins2demo'
    ANYPOINT_CREDS = credentials('anypoint.credentials')
    ANYPOINT_ENV = 'Sandbox'
    ANYPOINT_BG = ''
    ANYPOINT_MULE_VER = '4.1.5'
    ANYPOINT_WORKER_SIZE = 'Small'
  }
  tools { 
    maven 'maven3'
  }
  stages {
    stage('MVN Build Deploy') {
      steps {
        sh 'mvn deploy -DskipTests -DmuleDeploy -Dcloud.env=$ANYPOINT_ENV -Danypoint.businessGroup=$ANYPOINT_BG -Dcloudhub.workerType=$ANYPOINT_WORKER_SIZE -DcloudhubAppName=$ANYPOINT_APP_NAME -Dmule.version=$ANYPOINT_MULE_VER -Dcloud.user=$ANYPOINT_CREDS_USR -Dcloud.password=$ANYPOINT_CREDS_PSW'
      }
    }
  }
}