node {
      checkout scm

      docker.image('node:6.9.4').inside {

        stage("Install NPM Dependencies") {
          sh "npm install"
        }

        stage("Build Application") {
          sh "npm run build"
        }

     }
}