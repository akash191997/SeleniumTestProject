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
            emailext body: '', subject: '', to: 'akashrathod451@gmail.com'
        }
    }
}
