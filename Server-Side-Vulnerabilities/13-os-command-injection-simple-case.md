# OS Command Injection, Simple Case

"Check stock" feature sends a `storeId` param that gets passed straight into a shell command server-side, no sanitization.

Tested with:
```
storeId=1;whoami
```
Response had the normal stock output plus the whoami result tacked on. Confirmed injection. Ran the lab's actual target command the same way and it solved.

**Fix:** don't shell out with user input at all if you can avoid it, and if you can't, sanitize hard or use a proper API instead of string concatenation.
