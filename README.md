# appstore

Public feature flags for the Colabio mobile app.

This repository holds one file, `app_policy.json`, served over
`raw.githubusercontent.com` so the app can read it without authentication.
It is public for that reason alone. It carries no credentials, no keys and
no private data — only flags that decide what the app shows.

## app_policy.json

| Key | Type | Meaning |
| --- | --- | --- |
| `showGoogleSignInButton` | bool | Whether the iOS build shows the Google Sign-In button. Android ignores this and always shows it. |

The app reads the flag on each launch and caches it for the life of the
process, so a change here reaches users on their next app start — no
release needed.

### Keep this `false` on iOS until Sign in with Apple ships

App Store Guideline 4.8 requires an equivalent privacy-focused login
wherever an app offers a third-party sign-in alongside in-app account
creation. The app has Google Sign-In and email signup but no Sign in with
Apple, so turning this on invites a rejection at review.

If the file is missing or unreadable, the app falls back to `false`.
# appstore
