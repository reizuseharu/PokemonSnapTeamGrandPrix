# Design Document

Pokémon Snap Team Grand Prix [*PSTGP*]

## 1. Considerations


#### 1.1 Assumptions
Each portion of PSTGP will be implemented on a rolling basis, slowly incrementing pieces as time passes and need arises. The only required portion will be a publicly available leaderboard, with all other portions capable of ad-hoc manual execution.

#### 1.2 Constraints
Each API of PSTGP will be implemented in a language best suited for its purpose (e.g. Kotlin for backend, TypeScript+React for frontend).

#### 1.3 System Environment
- APIs will be hosted on an EC2 machine in AWS to allow constant availability
- Static documents will be hosted in S3 or gist.github.com for easy editing and constant access

## 2. Architecture


#### 2.1 Overview

##### Schedule
Schedule will be implemented using Calendly. Manually, team leaders will schedule a match with an opposing team each week, validing the team with a Tournament Commentator (TC). After all 3 agree, a match should be created on Calendly by the TC using a provided template.

The Schedule API will use Calendly's public API to update the [PSTGP Home Page](tgp.pkmnsnap.com) and [PSTGP Schedule Page](tgp.pkmnsnap.com/schedule) with the upcoming race.

##### Leaderboard
The Leaderboard will exist as standings to record the results of each race. It will contain match results, individual runner results, and other miscellanous race information. A REST API will underly a UI for use by editors of the leaderboard. The leaderboard will allow users to insert, update, and remove race results (only highest access can remove -- only for accidental inputs).

The Leaderboard API will update the [PSTGP Home Page](tgp.pkmnsnap.com) and [PSTGP Leaderboard Page](tgp.pkmnsnap.com/standings) with results.

The Tournament Organizer (and select Administrators) will be allowed to update the Leaderboard. The leaderboard should be updated after every team race is complete.

##### Stream Widgets

###### Snap Facts
Pokémon Snap contains stages showing many different environments. During the speedrun however, there are many times when looking directly up to the sky is the intended fastest strategy -- making all the environment go to waste. So as a joke, many of the Pokémon Snap community mention `Beach Facts` or `Valley Facts` (the two most Sky facing stages) as a request to the commentators.

Snap Facts is the evolution of that -- a randomly selected blurb from a list of facts about each environment that exists in Pokémon Snap.

*If possible, it would match the stage a runner is on automatically

Snap Facts will be several files simply containing facts for each stage. Preloaded, randomized, and then popped off of a queue to ensure no repeated facts during a stream.

###### Race Standings
In a regular event, showing the currently winning runner is simple: show best completed time, or current pace. As team event, it becomes much more difficult to show a team's position across all current runs. Race Standings will be a method of gathering all current paces, and completed runs to show the (as current as possible) score.

Commentators will be allowed to put in the current completed run times and paces of runner using a UI. These times and paces will be compiled into a database which will be accessible through a REST API call. Calling this API will return the current expected team scores, assuming no changes -- using split times for each runner.

Race standings will require PB times for each runner for accuracy.

Race standings will require split times for each runner entering the PSTGP for best accuracy.

###### Runner Info
Each speedrunner has a history with Pokémon Snap. Whether they have been around since the early days, when sub 22 was a brilliant time; or if they've recently joined and shot to the top along with the other Canadian giants. Runner Info is for having blurbs for each runner, while they are running.

Runner Info can contain information about strategies found (famously or infamously) by a runner, their current PB, current or previous WRs held of any category, rivalries, or simply anything related -- like their favorite Pokémon.

Runner Info is to remind viewers and runners that this is for fun, even if there is only one winner. Well, one team winner.

Runner Info will be implemented as a set of static information about each runner which is shown at random, but can repeat. It will be accessed through a REST API. Eventually, there will be a method to submit more blurbs, but will have to be reviewed by a TO before acceptance.

#### 2.2 Component Diagrams
*Provide here the diagram and a detailed description of its most valuable parts. There may be multiple diagrams. Include a description for each diagram. Subsections can be used to list components and their descriptions.*

#### 2.3 Class Diagrams
*Provide here any class diagrams needed to illustrate the application. These can be ordered by which component they construct or contribute to. If there is any ambiguity in the diagram or if any piece needs more description provide it here as well in a subsection.*

#### 2.4 Sequence Diagrams
*Provide here any sequence diagrams. If possible list the use case they contribute to or solve. Provide descriptions if possible.*

#### 2.5 Deployment Diagrams
*Provide here the deployment diagram for the system including any information needed to describe it. Also, include any information needed to describe future scaling of the system.*

#### 2.6 Other Diagrams
*Provide here any additional diagrams and their descriptions in subsections.*

## 3 User Interface Design
*Provide here any user interface mock-ups or templates. Include explanations to describe the screen flow or progression.*

## 4 Appendices and References


#### 4.1 Definitions and Abbreviations
*List here any definitions or abbreviations that could be used to help a new team member understand any jargon that is frequently referenced in the design document.*

#### 4.2 References
*List here any references that can be used to give extra information on a topic found in the design document. These references can be referred to using superscript in the rest of the document.*
