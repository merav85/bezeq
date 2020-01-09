pipeline {
   agent any
   tools { 
      'Maven 3.6.3'
   }
   stages {
      stage('Build') {
        steps {
          echo 'Building...'
          echo "Running ${env.BUILD_ID} ${env.BUILD_DISPLAY_NAME} on ${env.NODE_NAME} and JOB ${env.JOB_NAME}"
          // Compile a Java file
          javac HelloWorld.java
          // Execute the compiled Java binary called HelloWorld
          java HelloWorld
          // Executes the Apache Maven commands, clean then package
          mvn clean package ./HelloPackage
          // List the files in current directory path by executing a default shell command
          sh "ls -ltr"          
        }
   }
   stage('Test') {
     steps {
        echo 'Testing...'
     }
   }
   stage('Deploy') {
     steps {
       echo 'Deploying...'
     }
   }
  }
}