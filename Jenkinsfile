pipeline{
    agent any
    stages {
        stage('upload to aws')
        {       
            stage('Lint HTML') {
              steps {
                  sh 'tidy -q -e *.html'
              }
            }
                 steps {
                  withAWS(region:'us-east-2',credentials:'aws static') 
                     {
                  sh 'echo "Uploading content with AWS creds"'
                      s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'jenkins.bucket.1')
                  }
              }
        }
    }
}
