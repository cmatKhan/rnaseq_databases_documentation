
## Contribution workflow
1. fork the repository into your own github account
2. clone the fork onto your local
3. __CRITICAL__: add a file called called `<organism>_database/.env`. It must be in `/<organism>_database` and it must be called `.env`. It must include at least the key value pairs included below, with correct values for your use case. Here is an example (__repeat__: the keys below are required for the site to function): 

```
DJANGO_SECRET_KEY=3AQ3YnmgnODOBPkXwIj3ybzu9t75c_VVFDyJNj2Kwbo
ALLOWED_HOST=["0.0.0.0", "localhost", "127.0.0.1"]
DJANGO_AWS_ACCESS_KEY_ID=""
DJANGO_AWS_SECRET_ACCESS_KEY=""
DJANGO_AWS_STORAGE_BUCKET_NAME=""
DJANGO_PAGINATION_LIMIT=100
DATABASE_NAME="<organism>_database"
DATABASE_USERNAME="your_username"
DATABASE_PASSWORD="your_password"
HOST_IP="127.0.0.1"
```
4. `npm install`. However, __NOTE__: There is an open issue as of 20210505 with a create-react-app dependency that conflicts with new versions of `npm`. To "fix" it currently, run `npm update --legacy-peer-deps` after `npm install`. Keep an eye on the issue though -- this should be resolved at some point. See this [issue report](https://github.com/facebook/create-react-app/issues/10811)

5. Look through the documentation, and the code. Choose an `@todo` to work on. Register the issue on the __brentlab__ github repo (not your fork). Please look through the `@todo` first, but if your issue isn't already noted in the `@todo`, just register a new issue on n the __brentlab__ github repo. 

- __Important__: If you have not configured your local computer for git, then [follow these instructions from git](https://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration). In particular, use the commit.template.

6. Create a branch (in your local repo), name it something descriptive related to the issue report, and knock out that `@todo`/issue. Use the 'issue' number as the Ticket: _number_ in your commit messages. Commit frequently. However, when your feature is done, squish down your commits so that the log isn't littered, rebase your branch, and merge with your master branch. [See this for help](https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase) or ask chasem@wustl.edu. Make sure your master branch on github is up to date with your local (including these git log revisions/etc), and issue a pull request to the __brentlab__ github repo.