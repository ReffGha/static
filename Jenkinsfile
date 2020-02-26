pipeline {
    agent any
    stages {
      stage('Lint HTML') {
        steps {
          sh 'tidy -q -e *.html'
         }
       }
      stage(‘AWSUploadS3’) {
        steps {
          withAWS(region:'us-west-2',credentials:'JenkinsAWS') {
            s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'udacityproject3reffatg')
          }
        }
      }
    }
}
