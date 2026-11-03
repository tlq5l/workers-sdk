---
"@cloudflare/workers-utils": patch
"wrangler": patch
---

Report a containers `authorized_keys` public key whose comment contains spaces

Before this change, a key such as `ssh-ed25519 AAAA... my laptop` passed the local config check. The deploy then failed with an API error, "Invalid Authorized Key format", that did not name the field. Wrangler now stops with an error that names `containers.authorized_keys[n].public_key` and asks for a one-word comment or none.
