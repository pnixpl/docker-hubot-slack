### Image details

* Based on node
* Hubot + hubot-slack adapter
* No SSH. Use docker exec or nsenter
* Supply HUBOT_SLACK_TOKEN or you won't get too far :)
* hubot might take a few minutes to connect to slack as it pulls the necessary node.js modules at startup
* hubot must be invited to channels
* Official hubot script repo: https://github.com/hubot-scripts


### Usage
You must first add the Hubot Slack app to your team to obtain a token. Search for it here https://slack.com/apps

#####Start hubot-slack with your own scripts
```
sudo docker run -d --name "hubot" -e HUBOT_SLACK_TOKEN=MY_HUBOT_SLACK_TOKEN -v /path/to/hubot/volume:/home/hubot/scripts jordan/hubot-slack:latest
```

#####Start hubot-slack with the help and pugme scripts
```
sudo docker run -d --name "hubot" -e HUBOT_SLACK_TOKEN=MY_HUBOT_SLACK_TOKEN -e EXTERNAL_SCRIPTS=hubot-help,hubot-pugme jordan/hubot-slack:latest
```

### Env vars
```
HUBOT_SLACK_TOKEN - Your hubot slack token
ENV HUBOT_NAME - myhubot (default)
ENV HUBOT_OWNER - none (default)
ENV HUBOT_DESCRIPTION - Hubot (default)
ENV EXTERNAL_SCRIPTS - hubot-help (default).  Do not add hubot-slack to this list as it is already installed and enabled in the container.
```

### Volumes
```
/etc/hubot/scripts
```
