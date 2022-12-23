pipeline {
     agent any
     stages {
         stage('Build') {
             steps {
                 sh 'echo "Hello World"'
                 sh '''
                     echo "Multiline shell steps works too"
                     ls -lah
                 '''
             }
         }      
         stage('Upload to AWS') {
              steps {
                  withAWS(region:'us-east-2',credentials:'jenkins-s3-cred') {
                      sh 'echo "Uploading content with AWS creds"'
                       //palash solaja rahul
                      s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'app.py', bucket:'jenkins1234jh')                       
                  }
              }
         }
     }
}
