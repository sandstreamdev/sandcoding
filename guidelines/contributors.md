# Contributors guide

For all repositories we use [All Contributors project](https://allcontributors.org/) to "reward each and every contribution, not just code."

To start using it in repository follow this [instruction](https://allcontributors.org/docs/en/bot/installation) to install bot.

Bot will simplify updating the contributor list in the `README` file. Short comment in PR (or issue) will generate new PR with updated `README` and contributors config file.

Remember to add as main contributor `sandstreamdevelopment`.
If you start with other contributors then to make `sandstreamdevelopment` first you'll have to manually edit `README` file and contributors config file.

First bot call should look like this:

`@all-contributors please add sandstreamdevelopment for business, financial, ideas`

For other contributors check possible [contribution types](https://allcontributors.org/docs/en/emoji-key) you can assign to them.

## NOTE :warning:

Please check bot's PR carefully as it may generate incorrect diffs where it removes all content and regenerates the contributors' list. If you find such a case then simply close that PR and try call the bot again with the same comment.
