node('linux'){
  
  stage('CheckOut Source') {
    checkout scm
  }

  stage('Build') {
    echo "Sample Build Step"
    sh 'zip mybuild.zip  -r . -x *.git*'
  }
  
  stage('Unit Tests') {
    echo "Sample Unit Tests"
  }
  
  stage('Integration Tests') {
    echo "Sample Integration Tests"
  }
  
  stage('publish to s3'){
    step([$class: 'S3BucketPublisher', dontWaitForConcurrentBuildCompletion: false, entries: [[bucket: 'jenkinstest3', excludedFile: '', flatten: false, gzipFiles: false, keepForever: false, managedArtifacts: true, noUploadOnFailure: true, selectedRegion: 'us-west-2', showDirectlyInBrowser: false, sourceFile: 'mybuild.zip', storageClass: 'STANDARD', uploadFromSlave: true, useServerSideEncryption: false]], profileName: 'jenkinstest3', userMetadata: []])
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
         