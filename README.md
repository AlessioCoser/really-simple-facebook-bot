# RSFB - Really Simple Facebook Bot

## Prerequisites
1. AWS account enabled and configured
2. Verify IAM Permissions
    - AWSLambdaFullAccess
    - IAMFullAccess
    - AmazonAPIGatewayAdministration

## Setup Facebook

1. clone repo
2. `npm install`
3. `npm run claudia -- create --region us-east-1 --api-module bot`
4. Configure Facebook Messenger App
    a. Associate App to a Page and copy `AccessToken`
5. `npm run claudia -- update --configure-fb-bot`
    a. Copy the below information:
       - `webhook URL`
       - `verify Token`
    b. You will be requested the below informations:
       - `Facebook Page Access Token`: is the access Token from page associated to the Facebook Messenger App
       - `Facebook App Secret`: is the app secret from Facebook Messenger App
6. Configure the WebHook into Facebook Developer App Console by insering `WebHook URL` and `Verify Token` from step 5a.
