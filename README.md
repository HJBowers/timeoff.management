## Team info:
[Goal 181 Respository Link](http://jsdev.learnersguild.org/goals/181-Timeoff_Snapshot-Approver_Epic.html)
```
Teamname: #drunk-civet
Authors: @lumodon, @HJBowers
```

# Quality Rubric

Code Construction: [40 points]
- Concise commenting
- Intermediate variables
- No long functions
- Well-factored self-documenting code
- Eslint is setup
Code Readability: [40 points]
- Good names for files, variables classes, methods etc.
- Consistent white space usage
- Comments explaining unusual code, bug fixes, code assumptions functions
- Clean, precise commit messages
Code Organization: [20 points]
- Methods are grouped logically or by accessibility. Basic separation of code into logical folders
- Code is grouped into regions and well commented with references to other source files. Each physical file has a unique purpose

# Specs for Review:

## Getting started

### Familiarize yourself with the codebase

1. First step of approaching a new codebase is to read the [README](README.md).
1. Next, get the code up and running. Checkout the [README](README.md) and look for instructions to get a local development copy of the repo up and running and play around with it.
1. Next, read the browse in the `t` directory. Reading test descriptions (and file names) is a great way to learn what the app can do.
1. Next, run all the tests locally, to make sure they are passing. (for this repo, there will be several failing tests) You'll need phantomjs installed: `npm install phantomjs` then run `npm test`
1. Next, checkout the [database design](docs/db_design.txt). Load it up in [sql designer](http://sql.apps.learnersguild.org/) and familiarize yourself with the schema.
1. Finally, look around the other folders and get a sense of how the code is organized, and what the technology stack is: database? front end? test suite? asset management? css framework?


## Epics

## Epic 1: New role: Approvers

This epics adds a new role: approver. Approvers can approve and reject requests, but don't have all of the admin access that an admin has.

- [X] As an Admin when I add a new user, I can choose to make them an approver<br>
- [X] As an Admin if I try to make someone an approver AND an admin I get an error: "User can only be approver or admin, not both"<br>
- [X] As an approver I can see a menu item in the top navbar next to calendar called "Requests" which links to "/requests"<br>
- [X] As an admin I can see the requests link as well<br>
- [X] As an employee I cannot see the requests link<br>
- [X] As an approver or admin, I can see a notification icon next to the request link that shows the number of pending requests<br>
- [X] As an approver, I can approve and reject requests<br>
- [X] As an approver, I do not have access to other admin functions (general, department, LDAP configuration, emails audit)<br>


# TimeOff.Management

Web application for managing employees absence.

[![Stories in Ready](https://badge.waffle.io/timeoff-management/application.png?label=ready&title=Ready)](https://waffle.io/timeoff-management/application)

<a href="https://travis-ci.org/timeoff-management/application"><img align="right" src="https://travis-ci.org/timeoff-management/application.svg?branch=master" alt="Build status" /></a>

## Features

**Multiple views of staff absence**

Calendar view, Team view, or Just plain list.

**Tune application to fit into your company policy**

Add custom absence types: Sickness, Maternity, Working from home, Birthday etc. Define if each uses vacation allowance.

Optionally limit the amount of days employee can take for each Leave type. E.g. no more than 10 days of Sick days per year.

Setup public holidays as well as company specific days off.

Group employees by departments: bring your organisation structure into, set the supervisor for every department.

**Third Party Calendar Integration**

Broadcast employees whereabout into external calendar providers: MS Outlook, Google Calendar, and iCal.

Create calendar feeds for individual, departments or entire company.

**Three Steps Workflow**

Employee request time off or revoke existing one.

Supervisor get email notification and decide about upcoming employee absence.

Absence is accounted. Peers are informed via team view or calendar feeds.

**Accesss control**

There are following types of users: employees, supervisors, and administrators.

Optional LDAP authentification: configure applicationto use your LDAP server for user authentication.

**Seamless data migration betweeen different installations**

User friendly and simple work-flow for data migration between different TimeOff.Management installations.

Admin user can download the entire company data as a single JSON file.

And then restore the account at different installation by simply uploading the JSON.

**Works on mobile phones**

The most used customer paths are mobile friendly:

* employee is able to request new leave from mobile device

* supervisor is able to record decision from the mobile as well.

**Lots of other little things that would make life easier**

Manually adjust employees allowance
e.g. employee has extra day in lieu.

Upon creation employee receives pro rata vacation allowance, depending on start date.

Users of three types: admins, supervisors, and employees.

Email notification to all involved parties.

Optionally allow employees to see the time off information of entire company regardless the department structure.

## Screenshots

![TimeOff.Management Screenshot](https://raw.githubusercontent.com/timeoff-management/application/master/public/img/readme_screenshot.png)

## Installation

### Cloud hosting

Visit http://timeoff.management/

Create company account and use cloud based version.

### Self hosting

Install TimeOff.Management application within your infrastructure:

(make sure you have Node.js and SQLite installed)

```bash
git clone https://github.com/timeoff-management/application.git timeoff-management
cd timeoff-management
npm install
npm start
```
Open http://localhost:3000/ in your browser.

## Run tests

We have quite a wide test coverage, to make sure that the main user paths work as expected.

Please run them frequently while developing the project.

```bash
npm test
```

(make sure that application with default settings is up and running)

Any bugfixes or enhancements should have good test coverage to get them into "master" branch.

## Updating existing instance with new code

In case one needs to patch existing instance of TimeOff.Managenent application with new version:

```bash
git fetch
git pull origin master
npm run-script db-update
npm start
```

## Feedback

Please report any issues or feedback to <a href="https://twitter.com/FreeTimeOffApp">twitter</a> or Email: pavlo at timeoff.management
