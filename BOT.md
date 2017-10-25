# Bot Milestone

## Use Cases — *Part 1 of 6*

We did not need to make any changes based on feedback from the design, however, some minor
changes were made since some functionality is only available to Slack Apps (i.e. \ commands).
Other than these changes, the use cases are simply duplicated below.

### Use Case 1: Configuring .travis.yml and .coveralls.yml

1. Precondition

* User must have Github api token in the system
* User needs to setup Github repo in Travis CI
* User has created a Node.js public project on Github

2. Main flow

  User will request configuring the .travis.yml and provide the name of public repo [S1].
  Bot asks for additional information that user must submit [S2]. Bot creates travis.yml
  file and pushes it to the repository [S3].

3. Subflows

  [S1] User provides init travis command with name of repo

  [S2] Bot will return list of techs that it supports (ex: Node, Ruby, etc.). And user
  confirms them.

  [S3] Bot creates template travis.yml file and pushes it to the repository. The bot notifies
  the Slack channel.

4. Alternative flows

  [E1] If the repository language is not supported, the bot will return an error message and gives
  the link for the Travis documentation.

### Use case 2: Creating issues if the build fails

1. Precondition

* User must have Github api token in system.
* The build should lead to a failure

2. Main flow

  Travis CI notifies bot of build failure along with the reason and uid of developer who started the build.
  Bot notifies developer of the failure and reason.
  Bot asks the developer if the failure calls for an issue to be created immediately [S1], add a different title/update assignees [S2] or not create the issue [S3].
  The bot creates an issue on the appropriate github repository branch.

3. Subflows

  [S1] The bot will auto-generate an issue name and auto-assign it to the developer who started the build. If the user accepts the auto-generated details, the issue is created immediately

  [S2] The bot will ask the developer for the issue title and to assign different people to the issue. Once the user enters these details, the issue is created by the bot

  [S3] If the user does not want to create an issue, the bot would not go forward with issue creation

4. Alternative flows

  [E1] If the build succeeds, the bot will not pass any messages to the user

  [E2] If the issue creation returns an error, the bot will relay that error to the user

### Use Case 3: Code coverage notifications

1. Precondition

* User must have Coveralls api token in system.
* Coveralls.io should be integrated with Travis CI
* Test suites have required proper coveralls files

2. Main flow

  When a push is made, the bot checks the coveralls coverage report.
  If a change is pushed resulting in a decrease in coverage, the bot will ask the developer if the failure calls for an issue to be created immediately [S2], add a different title/update assignees [S3] or not create the issue [S4].
  The bot will create an issue to implement necessary test cases for the delivered code

3. Subflows

  [S1] When setting up the bot, the developers have the ability to set the notification threshold

  [S2] The bot will auto-generate an issue name and auto-assign it to the developer who started the build. If the user accepts the auto-generated details, the issue is created immediately

  [S3] The bot will ask the developer for the issue title and to assign different people to the issue. Once the user enters these details, the issue is created by the bot.

  [S4] If the user does not want to create an issue, the bot would not go forward with the issue creation.

4. Alternative flows

  [E1] No test cases have been written to hook into Coveralls

## Mocking — *Part 2 of 6*

Service interactions with GitHub, TravisCI, and Coveralls have been mocked for all methods.
The `.json` files containing the mock data can be found in the [mocks](https://github.ncsu.edu/CiBot/bot/tree/master/node/modules/mocks) directory within
the modules.

In order to allow the main module (`bot.js`) to be agnostic to mocking, all patching
is done within the modules making the module calls. This also allows mocking of urls that include
custom parameters (i.e. GitHub contributor/file names). Since the mocking response does not change
from one call to another, however, we are unable to test some of the alternative flows at this time.

## Bot Implementation — *Part 3 of 6*

The bot implementation has been divided into four modules. All modules other than the main
module are contained within the [modules](https://github.ncsu.edu/CiBot/bot/tree/master/node/modules) directory.

* `bot.js` - This is the main bot module that handles all communication with Slack. Additionally,
it mediates all communication between the other modules.
* `github.js` - This module integrates with the GitHub service. It performs any necessary GitHub actions like
creating issues and files
* `travis.js` - This module integrates with the TravisCI service. Its main functionality is to pass a
message to `bot.js` when a build error occurs and to create valid `.yml` files to configure TravisCI.
* `coveralls.js` - This module integrates with the Coveralls service. Its main functionality is to pass a
message to `bot.js` when a coverage issue needs reporting and to create valid `.yml` files to configure
TravisCI. In determining when a coverage issue needs to be reported, this module can also set a coverage
threshold.

The primary responsibility of developers was roughly broken down along these modules.

| User ID | Responsibility |
| ------- | -------------- |
| ajmcnama | system architecture; selenium testing - setup helper methods and test help; help with `github.js` issue generation; general coordination, tracking, and debugging assistance |
| igibek<sup>[1](#foot)</sup> | `travis.js`; related selenium testing |
| sgonsal | `coveralls.js`; related selenium testing |
| sssaha2<sup>[2](#foot)</sup> | `bot.js`; assisted with integrating other modules into `bot.js` |
| tmdement | `github.js`; related selenium testing |

<a name="foot">1</a>: While igibek performed his work throughout the milestone, this work does not show up in the contributors section due to an issue with having the wrong email address associated with the commits.

<a name="foot">2</a>: While sssaha2 performed his work throughout the milestone, this work does not show up in the contributors section due to an issue with having the wrong email address associated with the commits.

## Selenium Testing — *Part 4 of 6*

Selenium tests have been implemented for all bot subflow interactions. The tests can be found in the [bot repo](https://github.ncsu.edu/CiBot/bot/blob/master/Selenium/src/test/java/selenium/tests/WebTest.java). For each command, we check to make sure that the bot responds with the correct command. We also test the flow of conversations necessary in several use cases.

In total, JUnit will run four different tests, one for each use case and a fourth one for the help message prompts.

## Task Tracking — *Part 5 of 6*

Task tracking for this milestone can be found in the [WORKSHEET](WORKSHEET.md#milestone-bot)

## Screencast — *Part 6 of 6*
