pipeline{
    agent {
        docker {
        image 'node'
        }
    }
    stages {
        stage('clone'){
            steps {
                git 'https://github.com/hathanhhai/vuecicd.git'
            }
        }
        stage('Information') {
            steps {
                sh 'node -v'
                sh 'npm -v'
            }
         }

        stage('Config') {
            steps {
                sh 'npm set registry https://registry.npm.taobao.org'
                sh 'npm set disturl https://npm.taobao.org/dist'
                sh 'npm set chromedriver_cdnurl http://cdn.npm.taobao.org/dist/chromedriver'
                sh 'npm set operadriver_cdnurl http://cdn.npm.taobao.org/dist/operadriver'
                sh 'npm set phantomjs_cdnurl http://cdn.npm.taobao.org/dist/phantomjs'
                sh 'npm set fse_binary_host_mirror https://npm.taobao.org/mirrors/fsevents'
                sh 'npm set sass_binary_site http://cdn.npm.taobao.org/dist/node-sass'
                sh 'npm set electron_mirror http://cdn.npm.taobao.org/dist/electron/'
            }
        }

        stage('Dependencies') {
            steps {
                sh 'npm install'
            }
        }
    }
}