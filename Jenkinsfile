pipeline{
  agent  any
  stages{
    stage('fetch code from SCM'){
      steps{
        echo'successfully fetched file from SCM'
      }
    }
    
    stage('validate file content from SCM'){
      steps{
        if(fileExists('index.html')){
          sh "grep -q '</html>' index.html"
          echo'validation is successfull'
        } else {
          error'fatal error'
        }
           }
           }
           
           
    stage('Deploy code to nginx server'){
      steps{
        sh 'cp index.html /usr/share/nginx/html/'
        sh 'cp image0.png /usr/share/nginx/html/'
        echo'deployment success'
      }
    }
  }

