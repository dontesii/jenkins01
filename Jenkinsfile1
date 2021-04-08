pipeline {
  agent any
  stages {
    stage('First step') {
      steps {
        sh 'echo "Hello "'
      }
    }
    stage('Two step') {
      steps {
        sh 'mysql -u root -p1Montecarlo1! -e \'SELECT * FROM tourneys;\' Users > /home/ubuntu/workspace/job3.1/test.txt'
      }
    }
    stage('Dump step') {
      steps {
        sh 'mysqldump -u root -p1Montecarlo1! Users > /home/ubuntu/workspace/job3.1/dump.sql'
      }
    }

   stage('S3Copy step') {
      steps {
      s3Upload consoleLogLevel: 'INFO', dontSetBuildResultOnFailure: false, dontWaitForConcurrentBuildCompletion: false, entries: [[bucket: 'jenkins33', excludedFile: 'Jenkinsfile', flatten: false, gzipFiles: false, keepForever: false, managedArtifacts: false, noUploadOnFailure: false, selectedRegion: 'us-east-1', showDirectlyInBrowser: false, sourceFile: '*/', storageClass: 'STANDARD', uploadFromSlave: false, useServerSideEncryption: false]], pluginFailureResultConstraint: 'FAILURE', profileName: 'Jenkins', userMetadata: [] 
      }
    }  
  }
}
