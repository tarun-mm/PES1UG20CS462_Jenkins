pipeline{
  agent any
  stages {
    stage('Build'){
      steps{
        sh 'g++ PES1UG20CS462.cpp -o PES1UG20CS462'
        build job : 'PES1UG20CS462-1'
        echo 'Build successful'
      }
    }
    stage('Test'){
      steps{
        sh './PES1UG20CS462'
        echo 'Test successful'
      }
    }
    stage('Deploy'){
      steps{
        echo 'Deploy successful'
      }
    }
  }
  post{
    always {
      script {
        if (currentBuild.result == 'FAILURE') {
          echo 'Pipeline build unsuccessful'
        }
      }
    }
  }
}
