# Workflow

To go with the heroku pipeline: Master is the production codebase and should stay as clean as possible.

A development workflow should be the following:

1. A developer picks a new issue (let's say "#42 answer the question")
2. He creates a new branch named accordingly (here: ticket/42_life_and_universe)
3. He works in it and finish the work + related tests. He makes multiple commits. All of the should reference the issue number (for example: "#42: Taking care of mice")
4. He creates a new pull-request (here: "For #42: Solving the ultimate question") to master for his job: Go to https://github.com/user/repo/pulls and click on "Create a new pull request".
5. His pull request description Must end with the line: "Closes: #42" so the issue will be automatically closed.
6. When he is satisfied with the state of his PR he assigns it to another dev.
7. The **Other** developer will do the code review. He can asks questions, suggests modifications and at the end approve the PR.
8. _IF_ The review apps have been activated in heroku, doing a test in it is the good time.
9. Merge the PR into master. It should be deployed in staging.
10. Verify that everything is fine in staging: The issue itself + an overall sanity test of the app. Having review apps activated **doesn't** remove the need to do this!
11. Promote staging to production is everything is fine otherwise, warn others of the problem and fix it ASAP in another branch and PR. Do not fix directly on master.

## Master branch protection

No one should be allowed to push code on the master branch. So in the settings of your app (settings/branches) add master as a protected branch.

## Code reviews

The code review consists in a thorough reading of the code.
It is very important to read everything, no details should be neglected.
If the reviewer judges that some changes are required, he explicitly writes what needs to be done and assigns the task to the developer.
The developer then makes the corrections and pushes his code on GitHub again (on the same branch, that will update the pull request) where the reviewer reads the code once more.
This goes on until the reviewer approves the code and authorizes the branch to be merged.

## Non regression checklist

Until integration tests are automated for this app, they should be done manually on the staging environment.
This means that each time an issue is over, the corresponding branch is merged on master and automatically deployed on the staging.
The developer in charge of the issue should visit the staging app and follow the steps of the non-regression check-list.
A non regression checklist is a list of actions to execute manually on the site in order to check that the application still behaves the way it should after a modification of code has been made.
"Non regression", refers to the fact that things that were working in a given way before the new code was pushed, should work the same war after the new code is pushed.

Don't forget to update your non-regression checklist as the features of your app grow and change.

## [Optional] Adding CircleCI to run unit tests and rubocop once more

### Why?

As always when it comes to automatic testing, to protect ourself (from ourselves).
CircleCi will run our test for us in "the cloud" for each pushed commit and prevent any pull-request to be merged if tests are not successful.

### Must have

- [ ] A CircleCI config (v2)
- [ ] CircleCI must run rubocop and rspec (with coverage)
- [ ] Github should wait for CircleCI to run before allowing merging (add a new protection on master branch)

### Reading list

- [CircleCi doc](https://circleci.com/docs/2.0/)
- [Example](https://github.com/denispasin/turtle_family/blob/master/.circleci/config.yml)

## [Very Optional] Adding Cypress.io to do integration testing

### Why?

You don't want to always do the regression testing over and over again.

### Must have

- [ ] Add cypress.io
- [ ] Test some basic workflows
- [ ] Add it as a new step in CircleCI

### Reading list

- [Cypress docs](https://docs.cypress.io/guides/overview/why-cypress.html#In-a-nutshell)
- [Example](https://github.com/denispasin/rails_to_webpack/commit/0fc4725252d0b576275ac2505a0187a8ca9e6c6f)
