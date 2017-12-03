# Report Milestone

## 1. Project Presentation

Please see the video demonstration below, which...

## 2. Report

### 2.1 Problem Solved by Bot

### 2.2 Primary Features and Screenshots

### 2.3 Reflection on the Development Process and Project

### 2.4 Limitations and Future Work
#### Limitations 

There are a few limitations of the bot we have to consider before using it on slack.
1. Currently only Node.js repositories are fully supported
2. Only one repository can be initialized on a particular slack channel
3. The owner of the Github repository has to have his/her Github token made known to the bot through a direct message to the bot
4. The repository which is to be monitored through slack should have the following software configuration set-up a priori 
    1. The repository should be connected to Travis CI, a configuration management tool which runs scripts based on build success or failures
    2. The repository should be added to Coveralls, an open source tool for getting information on code coverage
    3. The repository should have a file containing test cases and a reference of this file needs to be in package.json file
#### Future Work

The following are some points which we think would be future enhancements to the bot and it’s functionality
1. We would like to extend the bot’s functionality to initialize multiple repositories in one channel
2. We would also like to add the ability to communicate with the bot to set up the testing frameworks (Mocha and Istanbul) through the slack chat interface itself, instead of having it as a prerequisite
3. Currently, the bot supports only NodeJS projects and possible future enhancement would be to extend the bot to support Java, Ruby and/or Python as well

## 3. Peer Evaluation
