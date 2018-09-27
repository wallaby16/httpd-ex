node('') {
  stage 'buildInDevelopment'
  openshiftBuild(namespace: 'development', buildConfig: 'httpd-ex', showBuildLogs: 'true')
  stage('Deploy approval'){
    input "Deploy to prod?"
    }
  stage 'deployInDevelopment'
  openshiftDeploy(namespace: 'development', deploymentConfig: 'httpd-ex')
  openshiftScale(namespace: 'development', deploymentConfig: 'httpd-ex',replicaCount: '2')
}
