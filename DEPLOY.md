# Deploy Milestone

## 1. Deployment Scripts

## 2. Passing Acceptance Testing
**Test account**: *CiBotTA*  
**Test repository**: *travis-test*  
**CiBot App**: *heroku-bot*  
**Acceptance tests**:
1. [add-token](#1-add-token-to-store-skip-if-you-are-ta)
2. [init travis and create yaml file](#2-initialize-travis-and-create-yaml-file)
3. [build failure and create issue](#3-build-failure-and-create-issue)
4. [coverage loss and create issue](#4-coverage-loss-and-create-issue)

### 1. Add Token to Store (skip if you are TA)
1. Type ```add-token testuser=token``` as a direct message to the Cibot to add **Github token** for the **testuser**. 
    - **Note**: for TA we have already setup token.
    - **Note**: for security reasons you need to type the command only with direct messages
    - **Note**: if commands is incorrect the CiBot displays error message.

### 2. Initialize Travis and Create Yaml File
Precondition: navigate to dedicated channel.
1. Type ```@heroku-bot init travis {owner}/{repo}``` to initialize travis for the repo. Replace *owner* and *repo* with *test account* and *test repository* respectively. 
    - The CiBot asks the user if he/she wants to create YAML file for the repo.
2. Type ```@heroku-bot yes``` to start conversation to create yaml file.
    - The CiBot will reply with the list of supported technologies.
3. Type ```node.js``` to create yaml file for Node.js project
    - SUCCESS: the bot will reply with success message and push the `.travis.yaml` file into root folder of repository.
    - FAIL: the bot will reply with error message.
    - **Note**: if the user types unsupported technology, the CiBot reply with error message
    - **Node**: if the user types supported technology, but incorrect for the project then the bot will create the yaml file. But remember that the project will always fail.

### 3. Build Failure and Create Issue
When build fails the bot will notify the dedicated channel, and asks if someone want to create an issue.
0. Change `isBuildSuccess` to `false` inside **build.config.json** file. This will trigger build failure in travis.
    - The Cibot will notify the dedicated channel after build fails. The user can create an issue.
1. Type ```@heroku-bot create issue``` inside channel where build failure notified.
    - SUCCESS: The bot will ask the user if he/she wants to change the issue title.
        1. Respond `no` to skip changing the default title of the issue.
            - The Cibot will ask for common separated users to assign to the issue.
2. Type ```@heroku-bot yes``` to change the title of the issue.
    - SUCCESS: The bot will ask for the new title of the issue.
        1. Change the title of the issue to any string you want.
3. Type ```@heroku-bot user1, user2``` to assign *user1* and *user2* to the issue.
    - SUCCESS: The bot will create the issue with specified title and assigned to specified users.
    - FAIL: The bot replies with error messages.

### 4. Coverage Loss and Create Issue
When new commits degrades the coverage of the code, the coverage loss will be triggered, and the bot notifies repository channel that coverage has been loss and asks if someone wants to create an issue.
1. Comment out all tests in file **test.js** to trigger the coverage loss.
2. After a build completes the coverage loss will be triggered and issue creation conversation starts. Goto 3.1 to create an issue.

## 3. Task Tracking

Task tracking for this milestone can be found in the [WORKSHEET](WORKSHEET.md#milestone-deploy).

## 4. Screencast

Please see the video demonstration below, which...
