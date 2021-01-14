pipeline {
  agent any
  stages {
    stage('Test-connectivity') {
      steps {
        echo 'hello'
        sh 'date'
      }
    }

    stage('Repo-cloning') {
      steps {
        git(url: 'https://github.com/MoSalah5/testMaven1.git', branch: 'master', poll: true)
      }
    }

    stage('Compile') {
      steps {
        sh 'mvn compile'
      }
    }

    stage('test') {
      steps {
        sh 'mvn test'
      }
    }

    stage('package') {
      steps {
        sh 'mvn package'
      }
    }

    stage('Report') {
      steps {
        junit '**/target/surefire-reports/*.xml'
      }
    }

  }
}