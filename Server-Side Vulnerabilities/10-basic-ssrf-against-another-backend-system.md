# Basic SSRF Against Another Back-End System

Same stock checker, same idea, but this time the target isn't the app itself, it's another machine on the internal network.

Swept through `192.168.0.x` on a guessed port using the `stockApi` param (Intruder made this quick), watching which IP actually returned something instead of timing out. Found one serving an internal admin panel. Pointed the same param at its delete endpoint, request went through.

**Fix:** never let user input decide the destination host of a server-side request, and segment internal networks so the app server can't freely reach everything.
