# PR Response Doc — CineLog Watchlist Feature

## AI Usage
<!-- Fill in at the end — how you used AI tools during this project -->

## Comment 1 — Rename
**What I did:** I used the Cmd+Shift+F command to find all instances of save_to_watchlist. I then went through each one and changed it to add_to_watchlist
**How I verified:** I verified this by asking Claude Code to take another glance at the codebase and run tests to make sure the app still works after the change. 

## Comment 2 — Deduplication
**What I did:** I first looked at the add_to_collection() function in services/collection_service.py to see how it handled deduplication. I then clarified with Claude Code whether I should add the error in the collection_service.py and import it (like the FilmNotFoundError) create it in services/watchlist_service.py. Claude explained why it should be in watchlist_service.py. I then followed the pattern in collection_service.py for the custom exception class definition, docstring update, and the logic in add_to_watchlist(). 
Now when a film is added, it checks to see if the film_id is already in the watchlist, if it is, then it raises the AlreadyInWatchlistError that explain the film is already in the watchlist. 
**How I verified:** I verified by asking Claude Code to test it and it created a short terminal script to test it. The script test passed. 

## Comment 3 — Missing test
**What I did:**
**How I verified:**

## Comment 4 — Default visibility
**My position:**
**Reasoning:**
**Tradeoff acknowledged:**

## Comment 5 — Sort order
**My position:**
**Reasoning:**
**Engagement with reviewer's point:**

## Comment 6 — Rebase
**What conflicted:**
**How I resolved it:**
**How I verified no conflict remains:**

## PR Description
<!-- Written at the end — feature overview, design decisions, manual testing steps -->