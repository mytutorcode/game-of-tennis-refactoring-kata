# Game of Tennis Refactoring Kata

# Time Limit

1 hour (60 mins)

# Situation

The Wimbledon Tennis Company employed a software developer to create a tennis scoring application.

Unfortunately, the developer has taken a new job before the application could be declared finished.

You have been hired by the company to evaluate the codebase of this application and make any necessary changes to it.

The desired outcome of this should be that the application functions and performs to the specified business requirements.

# Business Rules 

The application uses the standard scoring rules for Tennis. 

| Points | Description |
|--------|-------------|
| 0      | Love        |
| 1      | Fifteen     |
| 2      | Thirty      |
| 3      | Forty       |
| 4      | Win         |

For a tennis player to win a game, they must win with at least a two point lead.

If the score is tied at 40 to 40 (what is called as a Deuce), a player must earn two consecutive points (an Advantage point and Point) to win the game. 

If the player who has an Advantage point loses the next point, then it reverts back to Deuce once again.

For the sake of simplicity, we are only implementing the scoring of **one** game.

### Example 1 - "Sarah wins"

| Bob | Sarah | Action       | Output         |
|-----|-------|--------------|----------------|
| 0   | 0     | Sarah scores | Love-All       |
| 0   | 15    | Bob scores   | Love-Fifteen   |
| 15  | 15    | Sarah scores | Fifteen-All    |
| 15  | 30    | Sarah scores | Fifteen-Thirty |
| 15  | 40    | Sarah scores | Fifteen-Forty  |
| 15  | Win   |              | Win for Sarah  |

### Example 2 - "Deuce"

| Bob | Sarah | Result       | Output            |
|-----|-------|--------------|-------------------|
| 0   | 0     | Bob scores   | Love-All          |
| 15  | 0     | Bob scores   | Fifteen-Love      |
| 30  | 0     | Sarah scores | Thirty-Love       |
| 30  | 15    | Sarah scores | Thirty-Fifteen    |
| 30  | 30    | Sarah scores | Thirty-All        |
| 30  | 40    | Bob scores   | Thirty-Forty      |
| 40  | 40    |              | Deuce             |

### Example 3 - "Advantage"

Advantage occurs when both players are at Deuce and one player scores, resulting in them having an advantage.

If they score again, they win.

| Bob | Sarah | Result       | Output              |
|-----|-------|--------------|---------------------|
| 40  | 40    | Sarah score  | Deuce               |
| 40  | Adv   | Sarah scores | Advantage for Sarah |
| 40  | Win   |              | Win for Sarah       |


# Application Overview

The application is built with **Spring Boot** and provides a single RESTful endpoint to score and report back the score for a given Game of Tennis.

The application also sends the score of the game to be displayed on a scoreboard seen by the audience.

There is no Database or other persistence being used by the application.


