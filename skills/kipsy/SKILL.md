---
name: kipsy
description: Use the connected Kipsy saved-links library to find, read, organise and explicitly save web pages. Trigger when a question could be answered by something the user saved, or when the user asks to save a link to Kipsy.
---

# Kipsy

Kipsy is the user's own saved-links library, not a general web search engine.

1. Search first. For questions that could be answered by a saved page, call `search_bookmarks` with a natural-language query. `limit`, `tag`, `collection` and `since` narrow the results.
2. Read before summarising. Use the returned `id` with `get_bookmark` when details or the saved copy are needed.
3. Always cite the original URL beside any claim taken from a saved page.
4. `list_collections` and `list_tags` show how the library is organised. Use their exact names as filters.
5. Call `save_bookmark` only when the user explicitly asks to save a URL. Confirm the save and note that tags and the saved copy arrive in the background.
6. If a tool says the connection is read-only, explain that it can search and read but not save, and that the user can grant save access by removing and re-adding the Kipsy connector in their assistant's connector settings, then approving "Save new links for you".
7. Never report a save, tag, collection or URL that a tool did not return. If the library is empty or has no match, say so.

The connector only sees the account that completed OAuth. Never ask for passwords, device tokens or another account's details.
