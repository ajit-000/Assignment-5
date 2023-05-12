pipeline{
    agent any
         tools{
              maven 'maven'
              jdk 'JDK17'
               }
     stages{
          stage('git' ){
            steps{
            git credentialsId:'github',url:'https://github.com/ajit-000/Assignment-5.git'
                 }
            }
          stage('build'){
            steps{
            bat 'mvn -f  Assignment-5/pom.xml clean install'
                 }
            }

          stage('code quality'){
            steps{
            withSonarQubeEnv('sonarQube'){
            bat 'mvn -f Assignment-5/pom.xml sonar:sonar'
                 }
           }
         }
     }
}
    
