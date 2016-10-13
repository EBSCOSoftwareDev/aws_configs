node('linux'){
  
  stage('CheckOut Source') {
    checkout scm
  }

  stage('Build') {
    echo "Sample Build Step"
  }
  
  stage('Unit Tests') {
    echo "Sample Unit Tests"
  }
  
  stage('Integration Tests') {
    echo "Sample Integration Tests"
    echo "$env.BRANCH_NAME"
  }
  
}
         