# Personal Assistant — public pages

Homepage, privacy policy, and terms of service for the Personal Assistant Google OAuth
client. Google requires all three to be publicly reachable before an external app can be
published to Production, and Production status is what avoids refresh tokens expiring
every 7 days.

Deliberately a **separate public repository** from the assistant itself, which stays
private. Nothing here is sensitive; nothing here should ever reference infrastructure
identifiers, endpoints, or account numbers.

## Published

Served from the `productivity-assistant-site` project repository via GitHub Pages:

- <https://ethan-dyas438.github.io/productivity-assistant-site/>
- <https://ethan-dyas438.github.io/productivity-assistant-site/privacy.html>
- <https://ethan-dyas438.github.io/productivity-assistant-site/terms.html>

All internal links are **relative** (`privacy.html`, not `/privacy.html`) so that the site
works from a project subpath. Root-absolute links would break here — keep them relative.

## Then, in Google Cloud → Google Auth Platform → Branding

- Authorized domain: `ethan-dyas438.github.io`
  (`github.io` is on the Public Suffix List, so the full hostname *is* the top private
  domain — this is what Google's "must be a top private domain" validator wants. Google
  authorizes domains, not paths, so the project subpath is irrelevant here.)
- Application home page: `https://ethan-dyas438.github.io/productivity-assistant-site/`
- Privacy policy: `https://ethan-dyas438.github.io/productivity-assistant-site/privacy.html`
- Terms of service: `https://ethan-dyas438.github.io/productivity-assistant-site/terms.html`
- **Leave the app logo empty** — uploading one triggers brand verification, which is
  exactly what we are avoiding.

Then Audience → **Publish app**. The unverified-app interstitial on first consent is
expected; click through via Advanced.

## Accuracy

These pages make factual claims about data handling. Keep them true as the project
changes — particularly the retention periods (90-day conversations, 5-year action log) and
the list of third-party processors (AWS/Bedrock, Open-Meteo).
