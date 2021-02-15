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

- No points are scored = Love
- 1 point scored = 15 points
- 2 points scored = 30 points
- 3 points scored = 40 points
- 4 points earned = set point (set over)

For a tennis player to win a game, he/she must win with at least a two point lead.

If the score is tied at 40 to 40 (what is called as a Deuce), a player must earn two consecutive points (an Advantage point and Point) to win the game. If the player who has an Advantage point loses the next point, the score will be Deuce once again.

For the sake of simplicity, we are only implementing the scoring for a single set (game) as opposed to a complete set or a match.

### Example 1 - "Sarah wins"

| Bob | Sarah | Action       | Game        |
|-----|-------|--------------|-------------|
| 0   | 0     | Sarah scores | -           |
| 0   | 15    | Bob scores   | -           |
| 15  | 15    | Sarah scores | -           |
| 15  | 30    | Sarah scores | -           |
| 15  | 40    | Sarah scores | -           |
| 15  | x     |              | Sarah wins  |

### Example 2 - "Deuce"

| Bob | Sarah | Result       | Game              |
|-----|-------|--------------|-------------------|
| 0   | 0     | Bob scores   | -                 |
| 15  | 0     | Bob scores   | -                 |
| 30  | 0     | Sarah scores | -                 |
| 30  | 15    | Sarah scores | -                 |
| 30  | 30    | Sarah scores | -                 |
| 30  | 40    | Bob scores   | -                 |
| 40  | 40    |              | (deuce)           |

# Application Overview

The application is built with **Spring Boot** and provides a single RESTful endpoint to score and report back the score for a given Game of Tennis.

The application also sends the score of the game to be displayed on a scoreboard seen by the audience.

There is no Database or other persistence being used by the application.


