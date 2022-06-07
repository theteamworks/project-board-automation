# Team process

In order to use this the team will need to follow this process. The intention is that this is as process-light as it can be for the development team when developing complex software products.

## Guiding principles

No one wants to waste time updating the board, everyone knows there is value in an accurate view on work being done.

### Planning with Issues

Its assumed that with this board automation the team is working with some planning process. Be it a Kanban style replenishment, or a Scrum type sprint planning; the team has the notion of a `todo` column and picks work items from this list to work on.

### Pull requests with no issue required

There are always exceptions to planned items, items may be so small that the overhead of creating issues and linking pull requests is both a waste of time and money.

In the event of a `crasher` type bug where work may be done immediately, or a minor refactor or fix, it's well understood that a no-issue pull request may be the best option.

In this case raise a pull request and add the `exclusion` label and continue the work and the PR will be added to the board and move as per the issue would.

### Use the review process in GitHub

This workflow has been set up around a flow that requires a pull request to merge into your `main` / `develop` branch. It also works with `CODEOWNERS` and any number of reviews required before being approved to merge. The GitHub repo settings can be seen [here](./GitHubSettings)

### Pick a card from `todo` and add your name(s) to it

Follow:

1. Pick a card from `todo`
1. Add your name(s) to it (pairing is cool)
    - if you forget linking a pull request or adding the exclusion label will add the item to the board
1. Work on your pull request as you would (draft -> reviews -> changes -> merge)
1. Voila, the board is updated automatically from `in-progress` to `merged`
1. Keep an eye on column lengths (WIP limits) to avoid starting more than you finish
1. Manually move the items `Done` after they have been deployed (don't let this column get too big - Aargh; big batch releases!).

Bingo!
