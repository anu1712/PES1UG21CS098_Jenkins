pipeline{
  agent any

  stages{
    stage('Clone repository'){
      steps{
        checkout([$class: 'GitSCM',
                  branches:[[name:'main']],
                  userRemoteConfigs:[[url:'https://github.com/anu1712/PES1UG21CS098_Jenkins.git']]])
      }
    }

    stage('Build'){
      steps{
        build job: 'PES1UG21CS098-1'
        sh 'g++ main.cpp -o output'
      }
    }

    stage('Test'){
      steps{
        sh 'this_command_does_not_exist'
      }
    }

    stage('Deploy'){
      steps{
        echo 'Deployment step'
      }
    }
  }

  post{
    failure{
      error 'Pipeline failed'
    }
  }
}
