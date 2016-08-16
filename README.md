ReUser Slack Onboarding Bot
-----

Deployed to: <http://reuser-onboarder-bot.herokuapp.com>

___

Forked and Modified from [outsideris](https://github.com/outsideris/)' [Slack Invite Automation](https://github.com/outsideris/slack-invite-automation "github/outsideris/slack-invite-automation")

___


## Setting
In `config.js`

* `slacktoken` : access token of slack.
  You can generate it in <https://api.slack.com/web#auth>.
  **You should generate the token in admin user, not owner.**
  If you generate the token in owner user, `missing_scope` error will be occurred.
* `inviteToken`: an optional security measure - if it is set, then this token will be required to get invited.
* `locale`: application language (currently `en`, `de`, `es`, `fr`, `pt`, `zh-CN`, `zh-TW`, `ja` and `ko` available).

  You can test your token via curl:

  ```shell
   curl -X POST 'https://YOUR-SLACK-TEAM.slack.com/api/users.admin.invite' \
   --data 'email=EMAIL&token=TOKEN&set_active=true' \
   --compressed
  ```

## Run
[Node.js](http://nodejs.org/) is required.

```command-line
$ cd slack-invite-automation
$ npm install
$ bin/www
```




## Run with Docker

It's easy to run this service if you have installed Docker on your system.

```command-line
$ git clone git@github.com:outsideris/slack-invite-automation.git
$ cd slack-invite-automation
$ docker build -t slack-invite-automation .
$ docker run -it --rm -e COMMUNITY_NAME="YOUR-TEAM-NAME" -e SLACK_URL="YOUR-TEAM.slack.com" -e SLACK_TOKEN="YOUR-ACCESS-TOKEN" -p 3000:3000 slack-invite-automation
```
From here you can access <http://localhost:3000> on your web browser.