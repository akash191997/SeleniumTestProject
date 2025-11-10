pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
         stage('Build') {
            steps {
                echo 'Building project'
            }
        }
         stage('Deploy') {
            steps {
                echo 'Deploying'
            }
        }
         stage('Test') {
            steps {
                echo 'Testing'
            }
        }
         stage('Release') {
            steps {
                echo 'Release the build into Production'
            }
        }
    }
    post
    {
        always
        {
            script {
                // Get build info
                def jobName = env.JOB_NAME
                def buildNumber = env.BUILD_NUMBER
                def buildStatus = currentBuild.currentResult
                // Get user who triggered the build
                def buildUser = ""
                wrap([$class: 'BuildUser']) {
                    buildUser = env.BUILD_USER_ID ?: "SYSTEM"
                }
            emailext body: '', recipientProviders: [buildUser()], subject: 'Pipeline status', to: 'akashrathod451@gmail.com'
        }
    }
}
