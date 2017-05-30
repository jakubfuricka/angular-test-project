node {
        stage("Build") {

            checkout scm

            docker.image('node:6.9.4').inside {

              stage("Install NPM Dependencies") {
                sh "npm install"
              }

              stage("Use Bundler to install dependencies") {
                sh "npm run build"
              }

           }

        }
}