# Github Action to delete comments by comment body

Delete-comment Action will delete comments from issues/prs by username. You can either 
specify an issue number on which to remove comments or let the action remove all comments
across the repository.

## Sample Manually Triggered Workflow

```yaml
name: delete comments by comment body name
on:
  workflow_dispatch:
jobs:
  delete-comments:
    runs-on: ubuntu-latest
    steps:
      - uses: mieszkoWrzeszczynskiMtab/delete-prev-comments@master
        with: 
          github_token: ${{ secrets.GITHUB_TOKEN }}
          comment_body: 'LCOV'
          issue_number: ${{ github.event.number }}  # remove comments from the current PR
```
