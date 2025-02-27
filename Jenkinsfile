pipeline {
   agent {         
      dockerfile {
            filename 'Dockerfile'            // Use your Dockerfile in the repo root
            dir '.'                         // Build context (root directory)
            additionalBuildArgs '--no-cache' // Optional: pass Docker build arguments
        } 
      }

   stages {
      stage('Tests') {
         steps {
            sh '/bin/bash -c "pytest"'
         }
      }
   }

   post {
       always {
           junit 'latest_test_results.xml'
       }
   }
}
