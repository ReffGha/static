pipeline {
    agent any
    stages {
      stage(‘AWSUploadS3’) {
        steps {
          withAWS(region:’us-east-2’,credentials:’JenkinsAWS’) {
            s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:’index.html’, bucket:’udacityproject3reffatg’)
          }
        }
      }
    }
}
