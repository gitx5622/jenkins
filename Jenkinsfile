node {
  try {
    stage('Checkout') {
      checkout scm
    }
    stage('Environment') {
      sh 'git --version'
      echo "Branch: ${env.BRANCH_NAME}"
      sh 'docker -v'
      sh 'printenv'
    }
    
    stage('Deploy'){
      if(env.BRANCH_NAME == 'master'){
      sh 'docker push localhost:5000'
      }
    }
  }
  catch (err) {
    throw err
  }
}
