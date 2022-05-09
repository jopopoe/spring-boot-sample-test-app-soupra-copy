pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Build incoming'
        bat 'mvn -B -DskipTests clean package'
        echo 'Build done'
      }
    }

  }
}