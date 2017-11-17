pipeline {
  agent any
  triggers {
    cron('* * * * *')
  }
  stages {
    stage('MailTest') {
      steps {
        sh 'echo date'
        mail(subject: 'Test-Mail', body: 'Version : ${env.BuildNumber} ; version1 : ${env.DeployVersion}', to: 'vinay.kumar@riversand.com', cc: 'sunil.agarwal@riversand.com')
      }
    }
  }
  environment {
    KEY_FOLDER_PATH = '/var/lib/jenkins/keys/'
    KEY_FILE_NAME = 'riversand-east-1.pem'
    REMOTE_SERVER = 'ubuntu@54.210.14.231'
  }
}
