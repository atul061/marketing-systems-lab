# Marketing systems lab

Small, practical tools and templates for marketing operations, built to make campaign work more consistent and easier to measure.

## Tool: UTM link builder (v7 rules)

[Open the UTM link builder](https://atul061.github.io/marketing-systems-lab/) to build a tracked link in five steps: landing page → parent campaign (`utm_id`) → activity → creative → where it's shared. The page builds `utm_campaign` and `utm_content` for you, fills in the medium for the source you pick, and draws a QR code you can download as a PNG.

The fields follow the v7 UTM rules:

- **`utm_source` is Title Case**, chosen from 18 fixed sources (`Instagram`, `WhatsApp`, `Google_Ad`, `Newspaper`…), because the CRM matches the exact spelling. The builder never changes the case.
- `utm_medium` is one of 11 lowercase values (`organic_social`, `organic_video`, `paid_social`, `messaging`, `offline`…).
- `utm_campaign` = `{utm_id}_{activity}_{nn}_{variant}`, e.g. `gsf28_b01_web_01_top`.
- `utm_content` = `{type}_{what}_{nn}`, e.g. `reel_topper_01`.
- `utm_term` only for paid ads.

Example: a GS Foundation 2028 topper reel on Instagram →
`…?utm_source=Instagram&utm_medium=organic_video&utm_campaign=gsf28_b01_wrks_01_top&utm_content=reel_topper_01&utm_id=gsf28_b01`

This page is a quick builder for anyone, with no login needed. Team links that must be shortened and saved go through UTM Studio in the internal Command Center.

## How this repository works

- `index.html`: the standalone UTM tool (runs entirely in the browser; nothing is sent to a server).
- `vendor/qrcode.min.js`: QR code library ([qrcodejs](https://github.com/davidshimjs/qrcodejs), MIT, see `vendor/qrcode.LICENSE`).
- Future tools will each include a short problem statement, usage instructions, and a metric they help improve.
- Changes are recorded as commits, so it's easy to see what changed and when.

**Data note:** use sample or approved public information in this repository. Keep lead lists, budgets, credentials, CRM exports, internal sheet links and unpublished company material out of public repositories.
