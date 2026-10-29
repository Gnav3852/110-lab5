Bug 1

- Looked at the console.log, /api/stat was 404
- Matched MenuScreenController.ts and index.ts
- Changed /api/stat to /api/stats

Bug 2

- Looked at Network stats response object
- Returned 0 so looked at index.ts
- Best was never getting updated in route

Bug 3

- Traced where the game set the lemon's "random" position (View)
- Rounding takes away the randomness 

Bug 4

- The issue is with the result screen playing the sound over and over again
- On init is called showResultsFromServer
- Results is init after we each the end of startTimer
- startTimer calls endGame but stopTimer which clears the timer isnt called
- This causes an infinite loop

Bug 5

- Looked at the leaderboard payload and saw that time is given properly
- index.ts saves entries as Time but LeaderboardEntry saves it as Timestamp 
- Fixed the mismatch in index.ts and leaderboard.json

Bug 6

- Leaderboard looks to be printing in desending order
- Comes from the response so its in index.ts
- Looked at .sort() and it has the wrong sort key

Bug 7

- Issue with parsing an empty json file
- Results calls updateLeaderboard to get the latest leaderboard which is /api/leaderboard
- Looking at loadLeaderboard() we don't handle that type of response so we get a parsing error