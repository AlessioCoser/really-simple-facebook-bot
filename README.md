# RSFB - Really Simple Facebook Bot
For more information you can check out [this blog post](https://claudiajs.com/tutorials/hello-world-chatbot.html) from ClaudiaJS.

## Setup AWS Account
If you are new to AWS you have to create an account and configure it to work on your computer, otherwise you can skip this section.

1. Register to [AWS](https://aws.amazon.com/)
2. Go to [IAM/Users](https://console.aws.amazon.com/iam/home#/users) and create an User
4. Add Permissions To User
  - AWSLambdaFullAccess (to create-update-delete Lambdas)
  - IAMFullAccess (to configure ClaudiaJs Executor Roles)
  - AmazonAPIGatewayAdministrator (to create HTTP Endpoints)
5. Go to tab 'Security Credentials' and create an **Access Key** and save the keys somewere in your computer
6. Install on your computer **awscli**
  - On Mac: `brew install awscli`
7. Run: `awscli configure` and add the Access keys required    


## Installation and first deploy
You don't need to install ClaudiaJS globally because it's a dependency of the project and is configured as a npm script.

1. Clone the project
   `git clone https://github.com/AlessioCoser/fb-bot-claudia.git`
2. Install dependencies
   `npm install`
3. Deploy the function
   `npm run claudia -- create --region us-east-1 --api-module bot`

## Configure with Facebook Messenger App

1. Go to [Facebook Developer page](https://developers.facebook.com/apps/)
2. Create new Facebook Messenger App
    - Associate it to a Page (or create a new page)
    - Copy its `AccessToken`
3. Run `npm run claudia -- update --configure-fb-bot`
4. Copy `webhook URL` and `verify Token`
5. You will be requested to enter
    - `Facebook Page Access Token`: the access Token from page associated to the Facebook Messenger App
    - `Facebook App Secret`: the app secret from Facebook Messenger App
4. Configure the WebHook into Facebook Developer App Console by insering `WebHook URL` and `Verify Token` from step **4**.
5. Publish your Facebook Messenger App
