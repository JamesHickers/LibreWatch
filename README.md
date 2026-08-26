<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:111827,35:1E3A8A,70:2563EB,100:38BDF8&height=220&section=header&text=LibreWatch&fontSize=46&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Independent%20Community%20Continuation&descAlignY=58" />
</p>

<p align="center">
  <strong>📺 Watch Together &nbsp;•&nbsp; 🛡️ Privacy &nbsp;•&nbsp; 🔓 Open Source &nbsp;•&nbsp; 🤝 Community</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/License-AGPL--3.0-blue.svg">
  <img src="https://img.shields.io/badge/Language-JavaScript-F7DF1E.svg">
  <img src="https://img.shields.io/badge/Status-Community%20Maintained-success.svg">
  <img src="https://img.shields.io/badge/Origin-Krynet%2C%20LLC-2563EB.svg">
</p>

---

> [!NOTE]
> **LibreWatch was originally created by Krynet, LLC as an open-source YouTube "Watch Together" framework for the Krynet ecosystem.**
>
> The original project was released under **AGPL-3.0**, allowing the software to be used, modified, and redistributed under the terms of that license.
>
> This repository is an **independent community-maintained continuation** of that work.

For information about **Krynet Community as an organization**, including its relationship with Krynet, LLC, security practices, UGC status, and community policies, see the organization's README.

---

## 📖 About

**LibreWatch** is an open-source framework for building privacy-conscious YouTube watch experiences.

Originally designed as a foundation for synchronized media playback within the Krynet ecosystem, LibreWatch provides a lightweight JavaScript architecture for:

* 🎥 YouTube playback
* 👥 Watch Together rooms
* 📋 Playlist management
* 💬 Chat
* 🛡️ URL privacy
* ⏭️ SponsorBlock integration
* 📱 Responsive interfaces

The community continuation aims to keep LibreWatch:

* 🔓 Free and open source
* 🌍 Self-hostable
* 🧱 Lightweight
* ⚡ Dependency-conscious
* 🛡️ Privacy-oriented
* 🤝 Community maintained

## ✨ Features

### 🎥 YouTube Playback

LibreWatch provides YouTube playback through **Plyr 3.7.8**.

Supported input formats include:

* 🔗 YouTube URLs
* 📱 YouTube Shorts URLs
* ▶️ YouTube embed URLs
* 🔗 `youtu.be` URLs
* 🌐 Piped URLs
* 🕵️ Invidious URLs
* 🔢 Raw 11-character YouTube video IDs

Standard controls include:

* ▶️ Play
* ⏸️ Pause
* ⏩ Seeking
* 🔊 Volume
* 🔇 Mute
* 🖥️ Fullscreen
* ⏱️ Playback position

---

### 🧹 URL Privacy

LibreWatch includes dynamic **ClearURLs** integration.

The system can:

* 📥 Fetch the global ClearURLs ruleset
* ⚙️ Compile provider-specific rules
* 🧹 Remove known tracking parameters
* 🔗 Apply provider URL-cleaning rules
* 🚫 Remove common identifiers
* 🛡️ Honor provider exceptions
* 🔗 Clean URLs before extracting YouTube video IDs

Known tracking patterns may include:

```text
utm_*
fbclid
gclid
```

If a URL cannot be safely parsed, LibreWatch preserves the original URL rather than attempting unsafe transformations.

---

### 🛡️ SponsorBlock

LibreWatch integrates SponsorBlock for automatic sponsor-segment skipping.

Features include:

* ⏭️ Sponsor-segment detection
* 📡 Configurable SponsorBlock endpoints
* 🔄 Fallback to `https://sponsor.ajay.app`
* 📊 Chronological segment sorting
* ⏩ Automatic sponsor skipping
* 💾 Browser caching
* ⏱️ Five-second network timeout
* 🚫 `no-referrer` requests

Built-in request controls include:

* 🪣 25-token request bucket
* 🔄 60-second token reset
* ⏱️ Four-second per-video cooldown
* 📡 Cross-tab coordination through `BroadcastChannel`

---

### 👥 Watch Rooms

LibreWatch includes room-based synchronization.

Users can:

* ➕ Create rooms
* 🔗 Join rooms using room codes
* 📋 Copy room codes
* 📡 View connection status
* 👥 View online participants
* 🔌 Handle room disconnections

Playback synchronization can include:

* 🎬 Video loading
* ▶️ Play
* ⏸️ Pause
* ⏩ Seeking
* 🕐 Playback position

---

### 📋 Playlist

LibreWatch includes a client-side playlist manager.

Features include:

* ➕ Add YouTube videos
* 🚫 Prevent duplicate entries
* 🏷️ Retrieve video titles through YouTube oEmbed
* 🖼️ Display thumbnails
* 🎬 Highlight the current video
* 🗑️ Remove videos
* ⏭️ Next video
* ⏮️ Previous video
* 🔄 Automatic advancement
* 🔀 Fisher-Yates shuffle
* ↩️ Restore original order
* 🧹 Clear the queue
* 📍 Track the current position

Playlist changes can also be synchronized with connected rooms.

---

### 💬 Chat

LibreWatch includes a lightweight chat system.

Features include:

* 👤 Random anonymous usernames
* 💾 Persistent username identity through `localStorage`
* ✏️ Custom usernames
* 🕐 Message timestamps
* 💬 Local/self message styling
* 🧠 In-memory message history
* 📏 500-character input limit
* 📡 Same-browser tab communication
* 🔄 Event-based message handling

---

### 🔔 UI Notifications

A lightweight toast system provides status feedback for events such as:

* ✅ Successful video loads
* ❌ Invalid URLs
* ⚠️ Failed video loads
* 🏠 Room creation
* 🔗 Room joining
* 🔌 Room disconnection
* ➕ Playlist additions
* 🧹 Playlist clearing
* 🔀 Playlist shuffling
* 📋 Room-code copying
* ⚠️ Player initialization failures

---

### 📱 Responsive Interface

The included interface supports:

* 🖥️ Desktop two-column layouts
* 📱 Mobile single-column layouts
* 🎥 Responsive playback
* 🎛️ Responsive controls
* 📱 Mobile-friendly controls
* 📋 Adjustable playlist and chat areas
* 🌙 Dark UI
* 🎨 CSS custom properties

---

## 🏗️ Architecture

LibreWatch uses small, focused JavaScript modules.

```text
📺 LibreWatch
│
├── 🎥 Player/
│   ├── playerCore.js
│   ├── youtubePlayer.js
│   ├── extract.js
│   ├── playlist.js
│   ├── chat.js
│   └── roomSync.js
│
├── ⚙️ Player/
│   └── config.json
│
└── 🌐 Web UI
    ├── index.html
    └── app.js
```

### 🧩 Core Components

| Module             | Responsibility                                                 |
| ------------------ | -------------------------------------------------------------- |
| `extract.js`       | 🧹 URL cleaning and YouTube ID extraction                      |
| `playerCore.js`    | ⚙️ Configuration, SponsorBlock, caching, and request limiting  |
| `youtubePlayer.js` | 🎥 Plyr initialization, playback, events, and sponsor skipping |
| `playlist.js`      | 📋 Queue management, navigation, shuffle, and auto-advance     |
| `chat.js`          | 💬 User identity and chat management                           |
| `roomSync.js`      | 👥 Room creation, joining, and synchronization                 |
| `app.js`           | 🔌 Connects the UI and application modules                     |
| `config.json`      | ⚙️ Player configuration                                        |

LibreWatch favors browser-native APIs where practical:

```text
fetch
URL
localStorage
BroadcastChannel
Cache API
AbortController
navigator.clipboard
```

---

## 🔐 Privacy & External Services

LibreWatch is designed to minimize unnecessary tracking and telemetry where the implementation can control it.

However, some functionality necessarily involves external services.

Depending on configuration and enabled features, requests may be made to:

* ▶️ YouTube
* 🛡️ SponsorBlock
* 🧹 ClearURLs resources
* 📦 CDN providers
* 👥 Room/synchronization services
* 🌐 Other configured external endpoints

The privacy practices, availability, logging, and security of those services are outside the control of LibreWatch.

> [!IMPORTANT]
> **LibreWatch is not an anonymity system.**
>
> Using LibreWatch does not prevent YouTube or other external services from receiving information about requests made to them.
>
> Users deploying their own instance should review the configured endpoints and understand what information is sent to each service.

---

## 🛡️ Deployment Considerations

Before deploying LibreWatch, particularly for a public or production instance, review:

* 🌐 Network endpoints
* 📦 JavaScript dependencies
* 💾 Local storage behavior
* 🍪 Cookies
* 📡 Room synchronization
* 🔗 External URLs
* 🧩 Third-party integrations
* ⚙️ Server configuration
* 🔐 Any authentication added by the deployment

LibreWatch is designed to be self-hostable, but the security of a deployment ultimately depends on how it is configured and exposed.

---

## 📁 Project Structure

```text
LibreWatch/
│
├── 📄 LICENSE
├── 📄 README.md
│
├── 🎥 Player/
│   ├── playerCore.js
│   ├── youtubePlayer.js
│   ├── extract.js
│   ├── playlist.js
│   ├── chat.js
│   ├── roomSync.js
│   └── config.json
│
└── 🌐 Web UI/
    ├── index.html
    └── app.js
```

Additional project files may be added as the community architecture evolves.

---

## 🛣️ Roadmap

Potential areas for future development include:

* 🔄 More robust Watch Together synchronization
* 💬 Full room-based chat synchronization
* 📋 Persistent shared playlists
* 👥 Improved participant management
* 🔐 Additional privacy protections
* 🎨 UI and accessibility improvements
* ⚡ Performance improvements
* 📡 More reliable synchronization
* 🧪 Automated testing
* 🐛 Compatibility fixes
* ⚙️ Additional player configuration
* 🌍 Better self-hosting support

Roadmap items are community development goals and may change as the project evolves.

---

## 🤝 Contributing

Contributions are welcome across:

* 🎥 Player functionality
* 👥 Watch-room synchronization
* 📋 Playlist functionality
* 💬 Chat
* 🛡️ Privacy
* 🎨 UI/UX
* ♿ Accessibility
* ⚡ Performance
* 📚 Documentation
* 🐛 Bug fixes
* 🧪 Testing

### 🧑‍💻 Contribution Principles

Please keep changes:

* 📖 Readable
* 🧩 Focused
* 📝 Documented
* 🔍 Reviewable
* ⚡ Lightweight
* 🛠️ Practical

LibreWatch should remain approachable for contributors rather than becoming an unnecessarily complicated framework.

---

## 🏛️ Original Project

LibreWatch was originally created by **Krynet, LLC** as an open-source component of the Krynet ecosystem.

The original project was released under the **GNU Affero General Public License v3.0 (AGPL-3.0)**.

### Official Resources

* 🌐 [Krynet.ai](https://krynet.ai)
* 📦 [Official Codeberg](https://codeberg.org/Krynet-LLC)
* 💻 [Official GitLab Mirror](https://gitlab.com/Krynet-Team)
* 🐙 [Legacy GitHub](https://github.com/Krynet-LLC)

This repository is an **independent community continuation** of the original project.

---

## 📜 License

LibreWatch is licensed under the **GNU Affero General Public License v3.0 (AGPL-3.0)**.

See [`LICENSE`](LICENSE) for the complete license terms.

---

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:111827,35:1E3A8A,70:2563EB,100:38BDF8&height=120&section=footer" />
</p>

<p align="center">
  📺 <strong>LibreWatch</strong> · 🛡️ Privacy · 🔓 Open Source · 🤝 Community Maintained
</p>

<p align="center">
  <sub>Independent community continuation of an originally open-source Krynet project.</sub>
</p>
