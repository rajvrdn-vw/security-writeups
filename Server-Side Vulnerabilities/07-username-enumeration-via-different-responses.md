# Username Enumeration via Different Responses

Tried a fake username + password, noted the error text and response length. Tried a real username + wrong password, error looked almost the same but length was slightly off.

That difference is the whole vuln. Sent the login request to Intruder, marked the username field, ran a wordlist through it (Community edition is throttled so this took a while). Sorted results by response length, one row stood out, that's the valid username.

Ran a second Intruder pass, username fixed, password field as payload this time. Sorted again, found the one that returned a 302 instead of 200. Logged in.

**Fix:** identical error message and response shape no matter which field was wrong. Rate limit attempts too.
