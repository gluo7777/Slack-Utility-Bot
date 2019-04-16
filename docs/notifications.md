# Notifications via Slack
User can ask bot to set notifications for new posts submitted to certain subreddit. These notifications will be sent on matching filters.

# Scenarios
## User-App flow
1. User => bot => enter following to set notification:
    - subreddit
    - title matching text
    - description matching text
2. User => bot => list of configured notifications
## Backend flow
3. 1) => Server => Persist
4. Reddit => Scraper => Matching Engine ~=> Webhook =>~ => Server => Bot => User
## Storage
- User (userId,userName,teamId,teamName,matcher)

## Limitations
- User needs to enable desktop notifications
- Can only scrape via Reddit's API and OAuth

## Enhancements
1. Utilize interactive components for user input instead of conversation
1. Option to be notified by email (use Gmail API?)

## Unknown
- Scrape other websites besides Reddit
- How well will this scale with 10^x users?
    - Need to implement load balancing, caching. 
    - Reuse matchers. Index regex and group users by regex.
    - Relational vs Nosql

# Action Items
- POC on nodejs vs [python frameworks](https://github.com/gluo7777/PythonRedditDealsBot) for consuming Reddit API
- Define DB Schema
- Define how posts will be matched
    - Define hierarchy of matching. E.g. 1 matcher for each subreddit => 1 sub-matcher for each user or for each similar regex