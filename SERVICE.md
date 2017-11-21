# Service Milestone

Please refer to the [bot](https://github.ncsu.edu/CiBot/bot) repo to view the current code base and commit history.

Please note that the number of commits is not necessarily reflective of work performed, particularly in the case of Igibek (ikoishy). The commits he has made reference his public GitHub account, and do not appear appropriately on the graphs.

The [Pivotal Tracker project page](https://www.pivotaltracker.com/n/projects/2118162) and [WORKSHEET](WORKSHEET.md#milestone-service) are more accurate reflections of individual work performed.

## 1. Use Cases

Descriptions of our three use cases can be found in the [Design](DESIGN.md) and [Bot](BOT.md) milestones.  Video demonstrations of the functional CiBot services for each use case can be found in the screencast embedded in the last section of this document. Links to the individual use case demonstrations can be found in the video description for quick reference.

Implementation details and relevant code for each use case is the same as described in the "Bot Implementation" section of the [BOT](BOT.md) document, with the exception of the following:

* A new `bot/node/data` directory has been created containing a `yamlLanguages.json`, a file that specifies the structure for Node.js and Ruby `.travis.yml` files for CiBot.
* A new `tokenManager.js` module has been included in `bot/node/modules` to enable our new `add-token` feature.
* A new `utils.js` module has been included in `bot/node/modules` that contains general-purpose methods that have been moved out of the `github.js` module.

## 2. Task Tracking

Task tracking for this milestone can be found in the [WORKSHEET](WORKSHEET.md#milestone-service).  For this milestone, we also included an **Assignees** column on the worksheet table to denote who completed work on the respective story, rather than include that information in a separate table here.  Individual work on distinct modules was roughly the same as was described in the "Bot Implementation" section of the [BOT](BOT.md) document, but as we move into more granular work, polishing, and bug fixes, the roles have begun to generalize.

## 3. Screencast

Please see the video demonstration below, which runs through each of the three use cases and shows how to use the new `add-token` feature.  Please note that sad paths and errors are almost exclusively handled through communication with the bot, and as such can be seen demonstrated in the [Bot Milestone screencast](https://www.youtube.com/watch?v=36JPuNsIBA8&list=PLD1SyWmTvl7MCFONNkLbTEOFX16C6J8CO&index=1).

[![CiBot Communication Demo](https://img.youtube.com/vi/CZL-Boh7SS4/0.jpg)](https://www.youtube.com/watch?v=CZL-Boh7SS4&index=2&list=PLD1SyWmTvl7MCFONNkLbTEOFX16C6J8CO)
