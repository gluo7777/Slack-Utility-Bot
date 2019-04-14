# Slack Utility Bot
Back end for the slack application that performs utility tasks such as setting notifications and querying public APIs.

## Features
Currently the following functionalities will be implemented:
- User can ask bot to returns tasks that are over due or needs to be done today. Can integrate with Google Tasks as back end.
- User can ask bot to set notifications for new posts submitted to certain subreddit. These notifications will be sent on matching filters.
- User can ask bot to calculate formulas. Example: What's the return in 7 years with this interest rate? What's my BMI?

## Stack
- Slack Application
    - OAuth Endpoints @/oauth
    - Interactive Components (Dialog, Menu, Buttons) @/slack/receive
- BotKit
    - Handles conversations, request/response middleware injection, event listeners
- Express
    - Handles authentication, manual installation
    - Inbound webhooks
- HandleBars
    - Global templating engine
- Mongo
    - Stores data about teams, users, and channels