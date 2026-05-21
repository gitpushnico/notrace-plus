# Privacy Notice

Last updated: 2026-05-21

## What this site does

NoTrace+ provides in-browser tools to:

- remove image metadata,
- strip tracking parameters from URLs,

and a search shortcut that opens DuckDuckGo in a new tab when you choose to search.

## Scope and limitations

Each part addresses a different privacy signal:

- **Photo metadata** (tool): Output images no longer contain EXIF or related metadata, but visual content in the photo may still be identifying.
- **URL tracking** (tool): Known tracking parameters are removed from URLs, but other tracking methods (cookies, fingerprinting, server-side logging, IP-based identification) are outside this tool’s scope.
- **Search** (shortcut): When you search, your query is sent to DuckDuckGo and DuckDuckGo receives your IP address, as with any direct web request to an external service. NoTrace+ does not log your query.

## Data handling model

- NoTrace+ is a static site (HTML/CSS/JS) with no application backend.
- Image processing and URL cleaning happen locally in the browser.
- The site is configured without analytics SDKs, ad pixels, and non-essential tracking cookies.

## Cookies and similar storage

NoTrace+ does not intentionally set non-essential tracking cookies for analytics or advertising.

## Third-party requests

- Fonts are self-hosted in this project (no Google Fonts CDN calls are required).
- Some links and tools can open external websites only after user interaction.
- If you use the search shortcut, your query is sent to DuckDuckGo and DuckDuckGo will receive your IP address, as with any direct web request.

## Trademarks (GitHub)

The site may display the GitHub **Invertocat** mark solely to link to this project’s source repository on GitHub. **GitHub, Inc. is not affiliated with this project** and does not endorse it. See `THIRD_PARTY_NOTICE.md` and GitHub’s [Logo – Brand Toolkit](https://brand.github.com/foundations/logo) for context.

## Security and transmission controls

The project includes browser security headers via `vercel.json`, including restrictive Content Security Policy directives intended to minimize outbound connections.

## Your choices

- You can use the metadata and URL tools without sending those inputs to NoTrace+ servers.
- You can choose whether to use external links or the search shortcut.

## Contact

Project owner: gitpushnico  
Repository: https://github.com/gitpushnico/notrace-plus

For compliance updates, see:

- `THIRD_PARTY_NOTICE.md`
