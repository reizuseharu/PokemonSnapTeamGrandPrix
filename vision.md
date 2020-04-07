# Vision Document

Pokémon Snap Team Grand Prix

## 1. Introduction
As a community, we have desired a race format that is both fair and interesting, in spite of the plague known as River Cloyster. In an effort to find a fun and consistent race format for all runners, we have attempted various ways of limiting RNG and putting closer skilled opponents against one another. These methods sparked an idea of a team race, one where an individual's skill and a particular run's RNG would be balanced by the other runners/runs.


## 2. Product / Solution Overview
Team Grand Prix would alleviate the risks of bad RNG and bad runs by having several races from different runners all contribute to one team score. Each runner would have an incentive to finish with the best possible time, even on bad runs in an attempt to gain more points for their team, alleviating an issue with lost runs midgame. Scheduling races as a team allows for shifted schedules compared to VS races.


## 3. Business Needs / Requirements
Runners of any skill level will be able to race and contribute to a win. Runners will avoid fear of RNG ruining a competition. Runners will be able to miss races without significant impact on a competition.

## 4. Major Features
Team Grand Prix would be a team race (alike Mario Kart's team races) where each team member would be ranked according to finishing time, but points would be contributed to team total.

### Team Points
Each team will have N runners (out of a total T) competing in each race. Winner of a race gets full points, and it decreases from there. There will be a big drop between 1st and 2nd (a lesser drop between 2nd and 3rd) to incentivize the top places.

e.g. In a 5v5 Team race, 1st place gets 10 points, 2nd gets 7 points, 3rd gets 5, 4-4, 5-3, 6-2, 7-10th place gets 1.

### Team Selection
Each team will have a leader who selects their members based on a Runner budget. Each leader will be free in their budget, but will choose later if they have a higher value. Each runner will be assigned a value based on current PB during the team draft. Each leader will alternate choosing members. This may be broadcast.

e.g. CC has a budget of 80 points and needs 6 team members. Quo [20], Eric [19], Drogie [19], Lvon [18], and Lemon [16] would be worth 92 points, making it impossible to gather all those members for a team.

### Race Scheduling
Each team leader will be responsible for coordinating enough members for any particular race, with a Runner budget for each race. (And a maximum amount of races per season?). Each race will require a minimum of X runners or all points will be forfeit to opposing team.

### Race Hosting
Hosts will cast the team leader's (or race vice captain's) run, as well as a table showing current completed times for each runner. Team scores should be displayed. If possible, update current pace/stage for each runner using point screen timing.


## 5. Scope and Limitations
- There must be a team limit to allow easier organization of races
- There must be a runner limit to allow easier organization of races
- There will only be minimal software automation in the inaugural Team Grand Prix, limited to score collection
- There will be a meeting to have team leaders to agree to controversial rules
- There will be a solution to race scheduling that will allow for weekly races without sacrificing competition
