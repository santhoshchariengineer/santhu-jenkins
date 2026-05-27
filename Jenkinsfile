pipeline {
    agent any
    
    stages {
        stage('fetch code from SCM') {
            steps {
                echo 'successfully fetched file from SCM'
            }
        }
        
        stage('validate file content from SCM') {
            steps {
                // This script block is mandatory for if-else statements in declarative pipelines
                script {
                    if (fileExists('index.html')) {
                        sh "grep -q '</html>' index.html"
                        echo 'validation is successful'
                    } else {
                        error 'fatal error: index.html not found'
                    }
                }
            }
        }
           
      stage('Deploy code to nginx server') {
    steps {
        echo 'Deploying application to Nginx...'
        
        // We verify the index.html file exists in our current shared workspace path
        sh 'ls -la index.html'
        
        echo 'Code is live on Nginx Server via shared Docker volumes!'
    }
}
            }
        }
}
