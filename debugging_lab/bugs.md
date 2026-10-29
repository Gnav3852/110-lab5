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
