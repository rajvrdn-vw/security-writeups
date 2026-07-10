# User ID Controlled by Request Parameter, Password Disclosure

Edit-account form pre-fills a hidden password field using an ID param that isn't checked against who's logged in.

Swapped the ID to `administrator`, response came back with the admin's actual plaintext password sitting in the form field. Logged out, logged in as admin with it, deleted the target user.

**Fix:** don't return passwords in any response ever, and validate the ID belongs to the current session before returning anything.
