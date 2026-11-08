---
id: 01a170fc-24c4-74ba-ab0f-d11cbe495b24
source: Local
kind: SaaS
owner: Owner
processor: Google Cloud
serves:
  - Answering
---

# id.blust.ch

> Signs readers in to the chat with ZITADEL, the identity service blust.ch runs at id.blust.ch in Google Cloud's Zurich region, by invitation only, and issues the token from which the chat server reads the models a reader may choose. Beside ZITADEL, in the same region, blust.ch runs the link check, a small service of its own that ZITADEL calls after every sign-in with Google or Microsoft: it links that account to an existing one by its address only where the provider proved the address and exactly one account holds it with its address verified, and it keeps nothing and logs no address and no token.

## Connects to

| System | As | Service | Carries | Via |
| --- | --- | --- | --- | --- |
| Sign in with Google | OpenID Connect | | Reader | HTTPS |
| Sign in with Microsoft | OpenID Connect | | Reader | HTTPS |

## Holds

| Concept | Data object | Access |
| --- | --- | --- |
| Reader | Reader account | master |

## References

| What | URL |
| --- | --- |
| The service's source, infrastructure and the owner's steps | https://github.com/robertblust/id-blust-ch |
