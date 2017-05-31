node {
      checkout scm

      docker.image('node:6.9.4').inside {

        stage('Install NPM Dependencies') {
          sh 'npm install'
        }

        stage('Build Application') {
          sh 'npm run build'
        }

        stage('Build Docker Image') {

          /* .. better to build own image containing all the dependencies .. */
          sh 'sudo apt-get install --no-install-recommends apt-transport-https curl software-properties-common'
          sh 'curl -fsSL "https://sks-keyservers.net/pks/lookup?op=get&search=0xee6d536cf7dc86e2d7d56f59a178ac6c6238f52e" | sudo apt-key add -'
          sh 'sudo add-apt-repository "deb https://packages.docker.com/1.13/apt/repo/ ubuntu-$(lsb_release -cs) main"'
          sh 'sudo apt-get update'
          sh 'sudo apt-get -y install docker-engine'

          sh 'docker build -t angular-test-project .'
        }
     }
}
