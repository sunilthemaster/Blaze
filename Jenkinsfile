pipeline {
  agent any
  stages {
    stage('User check') {
      parallel {
        stage('User check') {
          steps {
            sh '''echo -e "\\n--------"
env > /home/jenkins/env.txt
cat /home/jenkins/env.txt
echo -e "\\n--------"

echo $BUILD_USER
echo $BUILD_USER_ID
echo $BUILD_USER_EMAIL

echo -e "\\n--------$USER-------"

if [ $USER == "admin" ]; then
    echo "Triggered by admin"
else
    echo "Triggered by $USER"
    exit 1
fi'''
          }
        }
        stage('send mail') {
          steps {
            mail(subject: 'testmail', body: 'testmail \\n newline', to: 'vinay.kumar@riversand.com')
          }
        }
      }
    }
  }
  environment {
    KEY_FOLDER_PATH = '/var/lib/jenkins/keys/'
    KEY_FILE_NAME = 'riversand-east-1.pem'
    REMOTE_SERVER = 'ubuntu@54.210.14.231'
  }
}