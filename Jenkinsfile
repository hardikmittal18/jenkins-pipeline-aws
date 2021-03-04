pipeline{
    agent any
    stages {
        stage('upload to aws')
        {
                 steps {
                  withAWS(region:'us-east-2a',credentials:'aws-static') 
                     {
                  sh 'echo "Uploading content with AWS creds"'
                      s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'jenkins.bucket.1')
                  }
              }
        }
    }
}
