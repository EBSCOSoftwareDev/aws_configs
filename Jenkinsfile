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
  
  //Return if not master
  if (env.BRANCH_NAME != "master"){
    echo "Is a feature branch, so no need for deployment"
    return
  }
    
  //Wait one hour for answer
  timeout(time: 1, unit: 'HOURS') {
    input 'Deploy to Development?'
  }
  
  stage ("Development Deployment"){
    
  }
  
  //TODO: Future deploy to QA
  //TODO: Future Run full QA Regression
  //TODO: Future Deploy to Production
  
}
         