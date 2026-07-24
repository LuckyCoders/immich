# Fork roadmap (LuckyCoders / Immich)

Plans for **this fork**, separate from the [upstream Immich roadmap](https://immich.app/roadmap).

Upstream deliberately **does not** add built-in 2FA / passkeys (see [discussion #8175](https://github.com/immich-app/immich/discussions/8175), [#3338](https://github.com/immich-app/immich/discussions/3338), [#15719](https://github.com/immich-app/immich/discussions/15719)) and recommends OAuth/OIDC instead. This document tracks what we want **in the fork** for our own instance.

## Auth / login security

| Status | Feature | Description |
|--------|---------|-------------|
| Planned | **TOTP (2FA)** | Optional login confirmation with an authenticator app code (Google Authenticator, Aegis, Bitwarden, …) |
| Planned | **Passkeys / WebAuthn** | Sign in with a browser or hardware key (KeyPass, YubiKey, Windows Hello, …) |

Goals:

- do not rely on Immich password alone for a publicly reachable instance;
- avoid requiring a full IdP (Authentik / Authelia) when lightweight built-in MFA is enough;
- features stay optional (off by default).

Related upstream comment: [immich#3338](https://github.com/immich-app/immich/discussions/3338#discussioncomment-17764669).

### Suggested stages (draft)

1. Server: TOTP secret / WebAuthn credential models; enroll + verify APIs at login.
2. Web: Account / Security settings UI + login challenge.
3. Mobile: TOTP on password login; passkeys where the platform allows.
4. Docs: how to enable; recovery codes backup.

## Other fork ideas (backlog)

| Status | Feature | Notes |
|--------|---------|-------|
| In progress / partial | Null `bucket_date` + personal APK | Photos tab crash fix; build via Actions |
| Upstream PR | Widget / asset deep-link L/R | [immich#30156](https://github.com/immich-app/immich/pull/30156) |
| Proposed upstream | Screenshots collection + hide from timeline | Comment on [immich#14449](https://github.com/immich-app/immich/discussions/14449) |
| Proposed upstream | Mobile: Merge people UI | [immich#30154](https://github.com/immich-app/immich/discussions/30154) |
| Later | Mobile merge people implementation | API already exists; app UI pending |

## Out of scope here

Face co-occurrence graph (“who appears with whom”) — personal experiment, not a fork Immich goal.
