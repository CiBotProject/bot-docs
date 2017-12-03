# Deploy Milestone

## 1. Deployment Scripts

The following steps can be followed to deploy CiBot to a remote server

* Ensure that ansible is installed
  * On ubuntu, this can be accomplished through `sudo apt-get update; sudo apt-get install ansible`
* Create the keyfile for the remote server you want to install on
  * This key file contains the private key to connect to the server
  * This file needs to have restricted access. Ansible will fail if it is group/world accessible, you can solve this using `chmod 600 keyfile`
* Specify the remote server you want to deploy to with an inventory file
  * This file has the format:
      ```
      [nodes]
      {{remote server ip address}} ansible_ssh_user={{username}} ansible_private_key_file={{path to private key for remote server}}```
      
* Setup the remote server, installing necessary packages
  * After the inventory/key file have been set up properly, run the setup playbook: `ansible-playbook setup.yml -i {{path to inventory file}}`
  * The `setup.yml` playbook can be found in the [bot/scripts](https://github.ncsu.edu/CiBot/bot/tree/master/scripts) directory.
* Start the app
  * After the server has been setup, start the app with ansible: `ansible-playbook startbot.yml -i {{path to inventory file}}`
  * The `startbot.yml` playbook can be found in the [bot/scripts](https://github.ncsu.edu/CiBot/bot/tree/master/scripts) directory. Before running it, however, the Slack API token needs to be inserted to replace the placeholder. 

## 2. Passing Acceptance Testing
*Note:* ***CiBot*** only supports public GitHub repositories.  
**Test account**: *CiBotTA*  
**Test repository**: *travis-test*  
**CiBot App**: *cibot*  
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
Preconditions: 
 * Navigate to dedicated channel
 * Ensure that you have activated Travis-CI for your account by logging in [here](https://travis-ci.org/)
 * Activate Coveralls for the repos by logging in [here](https://coveralls.io/repos/new)
 * **Note**: Due to limitations of the Coveralls API, you will need to manually toggle the Coveralls button next to a repo in order to use CiBot's coverage notification system for that repo (this has been done for CiBotTA/travis-test, but if you are testing other repos, this will need to be done first).
 
1. Type ```@cibot init travis {owner}/{repo}``` to initialize travis for the repo. Replace *owner* and *repo* with *test account* and *test repository* respectively. 
    - The CiBot asks the user if he/she wants to create YAML file for the repo.
2. Type ```@cibot yes``` to start conversation to create yaml file.
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
1. Type ```@cibot create issue``` inside channel where build failure notified.
    - SUCCESS: The bot will ask the user if he/she wants to change the issue title. By default the bot will set the title of the issue to the commit id which led to the build failure.
        1. Type `no` to skip changing the default title of the issue.
            - The Cibot will ask for comma separated users to assign to the issue.
            - Type `CiBotTA` to assign *CiBotTA* to the issue.
                - SUCCESS: The bot will create the issue with specified title and assigned to specified users.
                - FAIL: The bot replies with error messages.
                - **Note**: If the user types incorrect github logins the issue will be created without assigning anybody.
        2. Type `yes` to change the title of the issue.
            - SUCCESS: The bot will ask for the new title of the issue.
            - Change the title of the issue to any string you want.
            - Type `CiBotTA` to assign *CiBotTA* to the issue.
                - SUCCESS: The bot will create the issue with specified title and assigned to specified users.
                - FAIL: The bot replies with error messages.
                - **Note**: If the user types incorrect github logins the issue will be created without assigning anybody.

### 4. Coverage Loss and Create Issue
When new commits degrades the coverage of the code, the coverage loss will be triggered, and the bot notifies repository channel that coverage has been loss and asks if someone wants to create an issue.
1. Comment out all tests in file **test.js** to trigger the coverage loss.
2. After a build completes the coverage loss will be triggered and issue creation conversation starts. Goto 3.1 to create an issue.

## 3. Task Tracking

Task tracking for this milestone can be found in the [WORKSHEET](WORKSHEET.md#milestone-deploy).

## 4. Screencast

Please see the video demonstration below, which describes our deployment process, summarizes our Ansible playbooks, and reviews our three use cases.

[![CiBot Deployment Demo](https://img.youtube.com/vi/X3ZxghDAxEk/0.jpg)](https://www.youtube.com/watch?v=X3ZxghDAxEk&list=PLD1SyWmTvl7MCFONNkLbTEOFX16C6J8CO&index=4)

