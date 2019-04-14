# Writing specs

When you write specs, there two steps:

1. Writing User Stories (US): high-level description of the app's comportment. No technical stuff here.
2. Writing Issues: Issues represent a chewable division of work for a developer.

## User Story

A user story should use [Gherkin](https://docs.cucumber.io/gherkin/reference/) format.
You should store each of them in a milestone of your repository. One per story. (https://github.com/user/project/milestones)
You can later attach issues to them and track their completion.

### Example

```gherkin
Feature: Login

  Scenario: User Login
    As a registered user
    I want to log in
    Because I want to access content
    Given I know my username/password
    When I go on sign-in page
    And enter my username and password
    And click on "Login"
    Then I'm logged in
    And I see "You are now logged in." notice

  Scenario: User Forgot password
    As a registered user
    I want to log in
    Because I want to access content
    Given I forgot my username/password
    When I go on sign-in page
    And click on "Forgot password"
    And enter my email
    And click on "Yes I have forgotten my password"
    Then I should receive an email with a link to reset my password
```

### Reading list

- [Pivotal guide to Gherkin](https://content.pivotal.io/blog/how-to-write-well-formed-user-stories)
- [User Story Guide](https://sobolevn.me/2019/02/engineering-guide-to-user-stories)

## Issue

An issue is a rather constraint amount of work.
Most of the time an Issue is related to a US (but not always, an issue for tech purposes only is valid).

An issue should have 3 criteria:

- **A rationnal**: in general I write this in "Why". The issue should explain why it's needed.
- **A description**: A long description should highlight as much as possible the differents points needed to succeed.
- **Some acceptance criteria**: A list of things that must be done to consider the issue as done (Must have).

Plus, each issue should have a score indicating its difficulty.

### Example

Title: User Login
Score: 3

```markdown
### Why

A user should be able to log in into the app to access pages

### To Do

- [ ] We should use Devise with a user model
- [ ] We should guard pages from being accessed without Login
- [ ] Remember to add stuff into regression testing document
- [ ] Log in button say: "Login"
- [ ] A notice should appear saying: "You are now logged in."
      […]

### Must Have

- [ ] Log in flow work
```
