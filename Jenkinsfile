pipeline {
  agent any
  stages {
    stage('MailTest') {
      steps {
        sh 'echo date'
        mail(subject: 'Test-Mail', body: 'Version : ${env.BuildNumber} ; version1 : ${env.DeployVersion}', to: 'sunil.agarwal@riversand.com')
      }
    }
    stage('User check') {
      steps {
        sh '''env.each { name, value -> println "Name: $name -> Value $value" }

echo -e "\\n--------$USER-------"

if [ $USER == "admin" ]; then
    echo "Triggered by admin"
else
    echo "Triggered by $USER"
    exit 1
fi'''
      }
    }
  }
  environment {
    KEY_FOLDER_PATH = '/var/lib/jenkins/keys/'
    KEY_FILE_NAME = 'riversand-east-1.pem'
    REMOTE_SERVER = 'ubuntu@54.210.14.231'
  }
}