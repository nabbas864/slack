node{
   stage('SCM Checkout'){
     git 'https://github.com/nabbas864/slack'
   }
   stage('Compile-Package'){
      // Get maven home path
      def mvnHome =  tool name: 'Maven-3', type: 'maven'   
      sh "${mvnHome}/bin/mvn package"
   }
   
   stage('Slack Notification'){
       slackSend baseUrl: 'https://hooks.slack.com/services/https://hoo/', channel: '#jenkins-norway', color: 'good', message: 'Jenkins notificationss, Slack!', teamDomain: 'slackdevOps', tokenCredentialId: 'slack-test1'
   }
}
