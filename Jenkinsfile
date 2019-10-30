pipeline {
agent any
  stages {


    stage ("Install Application Dependencies") {
      steps{
        sh '''
            pip install --user -r requirements.txt
           '''
      }
    }



    stage('test') {
      steps {
      sh '''
          source bin/activate
          sh 'python test.py'
          deactivate
         '''
      }
      post {
        always {
          junit 'test-reports/*.xml'
        }
      }
    }
  }
}
