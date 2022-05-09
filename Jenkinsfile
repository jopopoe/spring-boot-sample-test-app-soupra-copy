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

    stage('Tests') {
      parallel {
        stage('Unit test') {
          steps {
            echo 'Unit test incoming'
            bat 'mvn -Dtest="com.example.testingweb.smoke.**" test'
            echo 'Unit test done'
          }
        }

        stage('Integration test') {
          steps {
            echo 'Integration test incoming'
            bat 'mvn -Dtest="com.example.testingweb.integration.**" test'
            echo 'Integration test done'
          }
        }

        stage('Functional test') {
          steps {
            echo 'Functional test incoming'
            bat 'mvn -Dtest="com.example.testingweb.functional.**" test'
            echo 'Functional test done'
          }
        }

      }
    }

    stage('Deployment') {
      steps {
        echo 'blabla'
        bat 'mvn -B -DskipTests install'
      }
    }

  }
}