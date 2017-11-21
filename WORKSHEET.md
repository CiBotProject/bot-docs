# CiBot Progress Worksheet

This file tracks the work for each week iteration in each of the milestones.

## MILESTONE: BOT

**Milestone Start:** Tue 03 Oct

**Milestone End:** Wed 25 Oct

### Week 1: *Wed 04 Oct - Tue 10 Oct*

| Deliverable   | Item/Status   |  Issues/Tasks
| ------------- | ------------  |  ------------
| N/A           | Set up the project | [Create project skeleton](https://www.pivotaltracker.com/story/show/151828848) [Setup initial Slack API](https://www.pivotaltracker.com/story/show/151828838)
| Use Case      | Configuring .yml files         | &nbsp;
| Subflow      | S1             |  &nbsp;
| Subflow      | S2             |  &nbsp;
| Subflow      | S3             |  &nbsp;
| Errorflow    | E1             |  &nbsp;
| Use Case      | Creating issues if build fails         | &nbsp;
| Subflow      | S1             |  &nbsp;
| Subflow      | S2             |  &nbsp;
| Subflow      | S3             |  &nbsp;
| Errorflow    | E1             |  &nbsp;
| Errorflow    | E2             |  &nbsp;
| Use Case      | Code coverage notifications        | &nbsp;
| Subflow      | S1             |  &nbsp;
| Subflow      | S2             |  &nbsp;
| Subflow      | S3             |  &nbsp;
| Subflow      | S4             |  &nbsp;
| Errorflow    | E1             |  &nbsp;
| Selenium Tests| Incomplete    | [Connect to SlackBot](https://www.pivotaltracker.com/story/show/151828818)

### Week 2: *Wed 11 Oct - Tue 17 Oct*

| Deliverable   | Item/Status   |  Issues/Tasks
| ------------- | ------------  |  ------------
| Use Case      | Configuring .yml files         | &nbsp;
| Subflow      | S1 - Incomplete |  [Determine .yaml files to create](https://www.pivotaltracker.com/story/show/151842516)
| Subflow      | S2             |  &nbsp;
| Subflow      | S3             |  [Create GitHub Issues](https://www.pivotaltracker.com/story/show/151858807)
| Errorflow    | E1             |  &nbsp;
| Use Case      | Creating issues if build fails         | &nbsp;
| Subflow      | S1             |  &nbsp;
| Subflow      | S2             |  &nbsp;
| Subflow      | S3             |  &nbsp;
| Errorflow    | E1             |  &nbsp;
| Errorflow    | E2             |  &nbsp;
| Use Case      | Code coverage notifications        | &nbsp;
| Subflow      | S1             |  &nbsp;
| Subflow      | S2             |  &nbsp;
| Subflow      | S3             |  &nbsp;
| Subflow      | S4             |  [Create GitHub Issues](https://www.pivotaltracker.com/story/show/151858807)
| Errorflow    | E1             |  &nbsp;
| Selenium Tests| Incomplete    |  &nbsp;

### Week 3: *Wed 18 Oct - Tue 24 Oct*

| Deliverable   | Item/Status   |  Issues/Tasks
| ------------- | ------------  |  ------------
| Use Case 1    | Configuring .yml files         | [Create mock GitHub objects](https://www.pivotaltracker.com/story/show/152128355)
| Subflow      | S1 - Complete  |  [Define initialization bot interaction](https://www.pivotaltracker.com/story/show/151842516)
| Subflow      | S2 - Complete  |  *work was not tracked*
| Subflow      | S3 - Complete  |  [Create yaml file](https://www.pivotaltracker.com/story/show/152128237) and [this](https://www.pivotaltracker.com/story/show/152125904); [Create yaml file and save to repo](https://www.pivotaltracker.com/story/show/151844248)
| Errorflow    | E1             |  &nbsp;
| Use Case 2    | Creating issues if build fails         | [Create a hook to trigger bot](https://www.pivotaltracker.com/story/show/151857866); [Create mock Travis objects](https://www.pivotaltracker.com/story/show/152128342)
| Subflow      | S1 - Complete  |  [Generate initial build failure issue](https://www.pivotaltracker.com/story/show/151858691); [Create hook to show build status](https://www.pivotaltracker.com/story/show/151857866)
| Subflow      | S2 - Complete  |  [Ask who should be assigned to the issue](https://www.pivotaltracker.com/story/show/151858774)
| Subflow      | S3 - Complete  |  [Cancel issue creation if desired](https://www.pivotaltracker.com/story/show/152221246)
| Errorflow    | E1             |  &nbsp;
| Errorflow    | E2             |  &nbsp;
| Use Case 3    | Code coverage notifications        | [Create a hook to trigger bot](https://www.pivotaltracker.com/story/show/151866344); [Create mock Coveralls objects](https://www.pivotaltracker.com/story/show/152128347)
| Subflow      | S1 - Complete  |  [Create interface to set threshold](https://www.pivotaltracker.com/story/show/151866425); [Create a hook to show a coverage message](https://www.pivotaltracker.com/story/show/151866344);[Save a coverage threshold for each channel](https://www.pivotaltracker.com/story/show/151866357) and [this](https://www.pivotaltracker.com/story/show/151866425)
| Subflow      | S2 - Complete  |  [Create initial coverage issue](https://www.pivotaltracker.com/story/show/151866365); [Generate new issue when code falls below threshold](https://www.pivotaltracker.com/story/show/151866365)
| Subflow      | S3 - Complete  |  [Ask who should be assigned to the issue](https://www.pivotaltracker.com/story/show/151866367)
| Subflow      | S4 - Complete  |  [Cancel issue creation if desired](https://www.pivotaltracker.com/story/show/152221246)
| Errorflow    | E1             |  &nbsp;
| Selenium Tests| Incomplete    |  [Start selenium testing to support user flow](https://www.pivotaltracker.com/story/show/151828959); [Selenium testing for UC1](https://www.pivotaltracker.com/story/show/152241264); [Selenium testing for UC2](https://www.pivotaltracker.com/story/show/152241271); [Selenium testing for UC3](https://www.pivotaltracker.com/story/show/152241299);
| General       | Complete      | [Implement CiBot help dialog](https://www.pivotaltracker.com/story/show/151841553)

## MILESTONE: SERVICE

**Milestone Start:** Tue 24 Oct

**Milestone End:** Tue 14 Nov

### Week 4: *Wed 25 Oct - Tue 31 Oct*

The CiBot team practiced agile development by planning slack into the development cycle, and took this week off.

### Week 5: *Wed 01 Nov - Tue 07 Nov*

| Category | Description | Status | Assignees | Link |
| --- | --- | --- |  --- | --- |
| *General* | Team meeting to identify and delegate tasks.  | Complete | *everyone* |  |
| *UC3* | Determine Coveralls badge link. | Complete | sgonsal | [#152450078](https://www.pivotaltracker.com/story/show/152450078) |

### Week 6: *Wed 08 Nov - Tue 14 Nov*

| Category | Description | Status | Assignees | Link |
| --- | --- |  --- | --- | --- |
| *General* | Team meeting to review task status schedule work session. | Complete | *everyone* | |
| *General* | Create a screencast for the Service milestone. | Complete | tmdement | [#152622394](https://www.pivotaltracker.com/story/show/152622394)
| *UC1* | Create Travis CI and Coveralls badging functionality for repo README.md files. | Complete | tmdement | [#152450117](https://www.pivotaltracker.com/story/show/152450117) |
| *UC1* | Change the `tokenManager.js` module to keep tokens in persistent storage. | Complete | ikoishy | [#152700891](https://www.pivotaltracker.com/story/show/152700891) |
| *UC1* | Implement functionality to set up GitHub tokens using CiBot. | Complete | sssaha2 | [#152451275](https://www.pivotaltracker.com/story/show/152451275) |
| *UC1* | Add functionality for CiBot to initially activate Travis CI for a repo. | Complete | ikoishy | [#151975140](https://www.pivotaltracker.com/story/show/151975140) |
| *UC1* | Restrict adding token function to direct messages only. | Complete | ajmcnama<br/>tmdement | [#152705301](https://www.pivotaltracker.com/story/show/152705301) |
| *UC1* | Report that a response is not supported and prompt for another. | Complete | sssaha2 | [#152222000](https://www.pivotaltracker.com/story/show/152222000) |
| *UC2* | Determine Travis CI badge link. | Complete | ikoishy | [#152450080](https://www.pivotaltracker.com/story/show/152450080) |
| *UC2* | Create a live test repo for Travis CI build failures. | Complete | sgonsal | [#152449929](https://www.pivotaltracker.com/story/show/152449929) |
| *UC3* | Create a live test repo for Coveralls coverage loss. | Complete | sgonsal | [#142449944](https://www.pivotaltracker.com/story/show/152449944) |
| *UC3* | Coveralls should automatically run with builds, and CiBot should notify coverage details. | Complete | ajmcnama<br/>sgonsal | [#151975142](https://www.pivotaltracker.com/story/show/151975142) |
| *UC3* | Set a default value for created issues to be assigned to. | Complete | sgonsal<br/>sssaha2 | [#152264288](https://www.pivotaltracker.com/story/show/152264288) |
| *UC2<br/>UC3* | Validate input when using CiBot to create issues. | Complete | sssaha2 | [#152221228](https://www.pivotaltracker.com/story/show/152221228) |
| *UC2<br/>UC3* | Ensure assignees can be assigned issues before attempting to. | Complete | ajmcnama | [#152706456](https://www.pivotaltracker.com/story/show/152706456) |
| *UC2<br/>UC3* | Set a default contributor (last committer) that CiBot uses for suggested issue assignment. | Complete | ikoishy<br/>sgonsal | [#152264301](https://www.pivotaltracker.com/story/show/152264301) |
| *UC1<br/>UC2<br/>UC3* | Specify a web address in the .travis.yml file that CiBot is listening to. | Complete | ajmcnama | [#152701474](https://www.pivotaltracker.com/story/show/152701474) |
| *UC1<br/>UC2<br/>UC3<br/>* | Set up connections between CiBot, Travis CI, Coveralls, and GitHub. | Complete | ajmcnama | [#151828939](https://www.pivotaltracker.com/story/show/151828939) |
| *UC1* | The Travis CI badge should be automatically added to the README.md file for a repo when Travis CI is set up. | Incomplete | tmdement | [#151972298](https://www.pivotaltracker.com/story/show/151972298) |
| *UC1* | The Coveralls badge should be automatically added to the README.md file for a repo when Coveralls is set up. | Incomplete | tmdement | [#151972296](https://www.pivotaltracker.com/story/show/151972296) |

## MILESTONE: DEPLOY

**Milestone Start:** Wed 08 Nov

**Milestone End:** Tue 28 Nov

### Week 7: *Wed 15 Nov - Tue 21 Nov*

### Week 8: *Wed 22 Nov - Tue 28 Nov*

## MILESTONE: REPORT

**Milestone Start:** Wed 08 Nov

**Milestone End:** Sun 03 Dec

### Week 9: *Wed 29 Nov - Tue 05 Dec*
