# User ID Controlled by Request Parameter, Unpredictable IDs

Account page pulls data via `/myaccount?id=<uuid>`. IDs are proper UUIDs so can't just increment them, but that doesn't mean much if there's no ownership check on the backend.

Found the target's UUID leaked in a blog comment (author id was exposed in the page). Swapped my `id` param for theirs, got their account data straight back including the API key the lab wanted.

**Fix:** check the requester actually owns the resource being requested. Random ID isn't the same as access control.
