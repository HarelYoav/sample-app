pipeline {
  agent any
  stages {
    stage("Build") {
      steps {
        sh "sudo npm install"
        sh "mkdir -p node_modules/.cache && chmod -R 777 node_modules/.cache"
        sh "sudo npm run build"
      }
    }
    stage("Deploy") {
      steps {
        sh "sudo rm -rf /var/www/jenkins-sample-app"
        sh "sudo cp -r ${WORKSPACE}/build/ /var/www/jenkins-sample-app/"
      }
    }
  }
}

