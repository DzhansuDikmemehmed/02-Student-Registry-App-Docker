pipeline{
   agent any
   stages{
    stage('NPM Install'){
        steps{
            bat 'npm install'
        }
    }
    stage('Run npm audit tests'){
        steps{
            bat 'napm audit'
        }
    }
    stage('Execute tests'){
        steps{
            bat 'npm test'
        }
    }
   } 
}