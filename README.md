# CreatorBlock

See who appears in a YouTube video before you watch it, and choose what happens to videos featuring creators you like or dislike.

CreatorBlock is a free browser extension. People in the community tag which creators appear in a video, and those creators show up as small badges on thumbnails. You pick a filter for each creator you care about, and CreatorBlock highlights, dims, or hides their videos in your lists.

## Features

- **Creator badges** on thumbnails on the home page, in search results, and in recommendations.
- **Four filters** you set per creator:
  - **Like**: green badge and outline. Nothing is hidden.
  - **Warn**: red badge and outline. Nothing is hidden.
  - **Dim**: the thumbnail fades and blurs until you hover over it.
  - **Hide**: the video is removed from the list.
- **Community tagging**: use the CreatorBlock button in the video player to add creators to a video, confirm (✓) a tag someone else made, or dispute it (✕).
- **My Filters**: a list in the toolbar popup. Only creators you add yourself are in it. Tagging a video never changes your filters.
- **Creator verification**: channel owners can prove they own a channel by putting a short code in one of their video descriptions. Their confirmations count for more, but they are never final: enough community votes can outweigh them.
- **On/off switch** in the popup.

Filters only change video thumbnails in lists. A video you open directly always plays, and Shorts are not filtered.

## Install

- **Chrome Web Store:** https://chromewebstore.google.com/detail/creatorblock/domjgpdaienbeocfkfgnadgiigmibanh
- **From source (Chrome, Brave, Edge, Opera):**
  1. Download or clone this repository.
  2. Open `chrome://extensions` and turn on **Developer mode**.
  3. Click **Load unpacked** and choose the folder that contains `manifest.json`.

## Privacy

The short version (the full policy is at https://amerabyad.github.io/creatorblock/privacy.html):

- **No accounts and no analytics.** Your filters, known creators, and settings stay in your browser's extension storage.
- **Looking up tags:** the extension does not send the IDs of the videos you see. It sends only the first 4 characters of a hash of each video ID, and the server answers for every video in that bucket. The extension then picks out the ones it needs.
- **Tagging and voting:** when you tag, confirm, or dispute, the video ID, the creator, and your vote are sent to the server.
- **Anonymous ID:** a random ID is created on your device. The server stores only a salted hash of it, to stop double voting and to remember which channels you have proven you own.
- **Network addresses:** requests pass through Cloudflare, which can see IP addresses. The server uses a salted hash of your address only for rate limiting.
- **Creator searches** go directly to youtube.com, not to the CreatorBlock server.

## How it works

- **Extension:** Manifest V3, plain JavaScript, no build step. It uses only the `storage` permission and access to `youtube.com`.
- **Server:** a Cloudflare Worker with a D1 database that stores tags, votes, and verified channel owners.

## Tags can be wrong

Tags come from the community. If a tag is wrong, use ✕ to dispute it.

## Support

Questions, bug reports, and feature requests: https://github.com/AmerAbyad/creatorblock/issues or amerabyad7071@gmail.com.

## Disclaimer

CreatorBlock is an independent project. It is not affiliated with, endorsed by, or sponsored by YouTube or Google.

## License

None
