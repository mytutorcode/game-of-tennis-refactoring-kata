# Refactoring-Kata

This is a working-ish application for a game of Tennis.

The application is built with Spring Boot and provide a single RESTful endpoint to score and report back the score for a given Game of Tennis.

The application also sends the score of the game to be displayed on a scoreboard seen by the audience.

The hypothetical scenario that this was implemented by a former developer, you have inherritted this work and now the business is demananding to move this to production. Hence, we need to take all the neccessary steps to ensure that this runs and performs well in production.

## The rules

As a refresher, here are the scoring rules of Tennis. For the sake of simplicity, we are only implementing the scoring for a single game as opposed to a complete set or a match.

- No points are scored = Love
- 1 point scored = 15 points
- 2 points scored = 30 points
- 3 points scored = 40 points
- 4 points earned = set point (set over)

For a tennis player to win a game, he/she must win with at least a two point lead.

If the score is tied at 40 to 40 (what is called as a Deuce), a player must earn two consecutive points (an Advantage point and Point) to win the game. If the player who has an Advantage point loses the next point, the score will be Deuce once again.
