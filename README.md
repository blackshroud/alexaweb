# alexaweb

Alexa in The Browser, see https://alexaweb.herokuapp.com for a demo

## Notes

The client uses getUserMeda to access the microphone, this mean it will only work in Chrome, Firefox, Opera and Edge, no IE and no Safari Support, also the latest version of Chrome requires that the page be served via https for anything other than localhost, running from heroku is therefore useful ;)

## Setup

This app was built for heroku, if you want to run locally or on another platform you will require python 2.7 and a local install of redis, you will then need to install the modules listed in requirements.txt

### Download this repo

You can do this by cloning the repo to your server of choice (local or whatever)

`git clone git@github.com:sammachin/alexaweb.git`

OR you can setup a heroku app and set a forked version of the git as the source (heroku talks your through it)

make a note of your app name and if you want to rename it with

`heroku apps:rename [yourappname]`

### Create a new Heroku app (optional)

`heroku create`
 Add redis
 `heroku addons:create heroku-redis:hobby-dev`

### Get AVS Credentials

Next you need to obtain a set of credentials from Amazon to use the Alexa Voice service, login at http://developer.amazon.com and Goto Alexa then Alexa Voice Service

You need to create a new product type as an Application, for the ID use what ever you like, create a new security profile and under the web settings allowed origins put the following;

http://localhost:5000 

http://localhost:5000/code 

Also if you are deploying to heroku add the heroku app url

Once you've got the security credentials put them into the creds.py file.

You will also need to set the redis URL in the creds file


### Deploy

`git add creds.py
git commit -m "updated creds"
git push heroku master`

### Run

`heroku open`

## Enjoy
