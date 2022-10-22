pipeline {
  agent any
  stages {
    stage("Build") {
      steps {
        sh "sudo npm install"
        sh "sudo mkdir -p node_modules/.cache && sudo chmod -R 777 node_modules/.cache"
        sh "sudo npm run build"
      }
    }
    stage("Deploy") {
      steps {
        sh "sudo rm -rf /var/www/sample-app"
        sh "sudo cp -r ${WORKSPACE}/build/ /var/www/sample-app/"
      }
    }
  }
}

