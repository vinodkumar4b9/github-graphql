pipeline {
    agent any

    stages {
        stage('release') {
            steps {
              withCredentials([string(credentialsId: 'token', variable: 'mysecret')])  {
                  sh '''curl -H "Authorization: bearer $mysecret" -X POST -d " \\
 { \\
   \\"query\\": \\"query { viewer { login id name repositories(first: 10) { edges { node { id description name nameWithOwner } } } } }\\" \\
 } \\
" https://api.github.com/graphql'''
                  
}
               }
        
        }
        
    }
}
