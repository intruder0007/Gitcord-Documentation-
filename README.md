# Gitcord

[![Node.js](https://img.shields.io/badge/Node.js-18%2B-339933?style=flat-square&logo=nodedotjs&logoColor=white)](https://nodejs.org)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES2022-F7DF1E?style=flat-square&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Discord.js](https://img.shields.io/badge/Discord.js-14.x-5865F2?style=flat-square&logo=discord&logoColor=white)](https://discord.js.org)
[![GitHub API](https://img.shields.io/badge/GitHub_API-v3%2Fv4-181717?style=flat-square&logo=github&logoColor=white)](https://docs.github.com/en/rest)
[![Express](https://img.shields.io/badge/Express-4.x-000000?style=flat-square&logo=express&logoColor=white)](https://expressjs.com)
[![Firebase](https://img.shields.io/badge/Firebase-Admin_12-FFCA28?style=flat-square&logo=firebase&logoColor=black)](https://firebase.google.com)
[![Redis](https://img.shields.io/badge/Redis-ioredis_5-DC382D?style=flat-square&logo=redis&logoColor=white)](https://redis.io)
[![AES-256](https://img.shields.io/badge/Encryption-AES--256--CBC-00897B?style=flat-square&logo=letsencrypt&logoColor=white)](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard)
[![OAuth 2.0](https://img.shields.io/badge/Auth-OAuth_2.0-4285F4?style=flat-square&logo=oauth&logoColor=white)](https://oauth.net/2/)
[![Platform](https://img.shields.io/badge/Platform-Discord-5865F2?style=flat-square&logo=discord&logoColor=white)](https://discord.com)
[![Status](https://img.shields.io/badge/Status-Live-brightgreen?style=flat-square)](https://discord.com)

> **GitHub management for Discord.** 37 slash commands. Zero context-switching.

Gitcord bridges your entire GitHub workflow into Discord — create repos, review PRs, manage issues, and ship releases without ever leaving your server. Built with Discord.js 14 Component V2 UI, AES-256-CBC encrypted token storage, and real-time GitHub webhooks.

---

## Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                         DISCORD CLIENT                          │
│                                                                 │
│   User types /command   →   Interaction Event                   │
└────────────────────────────┬────────────────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────────┐
│                       GITCORD BOT (Node.js)                     │
│                                                                 │
│  ┌──────────────┐   ┌──────────────┐   ┌──────────────────┐   │
│  │  Command     │   │  Event       │   │  Express OAuth   │   │
│  │  Router      │   │  Handlers    │   │  Server :3000    │   │
│  │  (37 cmds)   │   │  (webhooks)  │   │  /auth/github    │   │
│  └──────┬───────┘   └──────┬───────┘   └────────┬─────────┘   │
│         │                  │                     │             │
│         └──────────────────┴─────────────────────┘             │
│                             │                                   │
│                    ┌────────▼────────┐                          │
│                    │  Core Services  │                          │
│                    │  • Auth Manager │                          │
│                    │  • Pagination   │                          │
│                    │  • Logger       │                          │
│                    │  • Formatters   │                          │
│                    └────────┬────────┘                          │
└─────────────────────────────┼───────────────────────────────────┘
                              │
           ┌──────────────────┼──────────────────┐
           │                  │                  │
           ▼                  ▼                  ▼
┌─────────────────┐  ┌────────────────┐  ┌──────────────────┐
│   GitHub API    │  │    Firebase    │  │      Redis       │
│   (@octokit/    │  │  Realtime DB   │  │   (ioredis 5)    │
│    rest v20)    │  │  AES-256-CBC   │  │   Rate limiting  │
│                 │  │  encrypted     │  │   & caching      │
│  REST + GraphQL │  │  token store   │  │                  │
└─────────────────┘  └────────────────┘  └──────────────────┘
```

---

## OAuth 2.0 Flow

```
Discord User                   Gitcord Bot              GitHub OAuth
     │                              │                        │
     │  /auth link                  │                        │
     │─────────────────────────────>│                        │
     │                              │                        │
     │  DM: auth URL + state        │                        │
     │<─────────────────────────────│                        │
     │                              │                        │
     │  Opens browser               │                        │
     │──────────────────────────────┼───── GET /authorize ──>│
     │                              │                        │
     │                              │                        │
     │                              │<──── redirect + code ──│
     │                              │                        │
     │                              │  POST /access_token    │
     │                              │────────────────────────>
     │                              │                        │
     │                              │<──── access_token ─────│
     │                              │                        │
     │                              │  AES-256-CBC encrypt   │
     │                              │  store → Firebase DB   │
     │                              │                        │
     │  DM: "Successfully linked!"  │                        │
     │<─────────────────────────────│                        │
     │                              │                        │
     │  /repo create my-project     │                        │
     │─────────────────────────────>│                        │
     │                              │  decrypt token         │
     │                              │  POST /user/repos ─────>
     │                              │<──── repo created ─────│
     │                              │                        │
     │  ✓ Repository created        │                        │
     │<─────────────────────────────│                        │
```

---

## Command Reference

### Repositories (8 commands)

| Command | Description |
|---------|-------------|
| `/repo create` | Create a new GitHub repository |
| `/repo list` | List your repositories with pagination |
| `/repo info` | Get detailed info about a repository |
| `/repo delete` | Delete a repository |
| `/repo fork` | Fork a repository |
| `/repo visibility` | Toggle public/private visibility |
| `/repo rename` | Rename a repository |
| `/repo topics` | Manage repository topics |

### Pull Requests (6 commands)

| Command | Description |
|---------|-------------|
| `/pr create` | Open a new pull request |
| `/pr list` | List open pull requests |
| `/pr view` | View PR details, diff, and comments |
| `/pr merge` | Merge a pull request |
| `/pr close` | Close a pull request |
| `/pr review` | Approve, request changes, or comment |

### Issues (5 commands)

| Command | Description |
|---------|-------------|
| `/issue create` | Create a new issue |
| `/issue list` | List issues with filters |
| `/issue view` | View issue details and comments |
| `/issue close` | Close an issue |
| `/issue assign` | Assign an issue to a user |

### Releases (4 commands)

| Command | Description |
|---------|-------------|
| `/release create` | Create a new release with tag |
| `/release list` | List all releases |
| `/release view` | View release notes and assets |
| `/release delete` | Delete a release |

### Gists (4 commands)

| Command | Description |
|---------|-------------|
| `/gist create` | Create a new gist |
| `/gist list` | List your gists |
| `/gist view` | View gist content |
| `/gist delete` | Delete a gist |

### Code & Search (4 commands)

| Command | Description |
|---------|-------------|
| `/search repos` | Search GitHub repositories |
| `/search code` | Search code across GitHub |
| `/search users` | Search GitHub users |
| `/file view` | View a file from any repository |

### User & Profile (3 commands)

| Command | Description |
|---------|-------------|
| `/profile` | View your GitHub profile summary |
| `/auth link` | Link your GitHub account via OAuth |
| `/auth unlink` | Unlink your GitHub account |

### Notifications (2 commands)

| Command | Description |
|---------|-------------|
| `/notify subscribe` | Subscribe to repo events |
| `/notify unsubscribe` | Unsubscribe from notifications |

### Utility (1 command)

| Command | Description |
|---------|-------------|
| `/help` | Show available commands |

---

## Tech Stack

| Layer | Technology | Version |
|-------|-----------|---------|
| Runtime | Node.js | ≥18 LTS |
| Discord | discord.js | 14.26.3 |
| GitHub API | @octokit/rest | 20.1.1 |
| Web Server | Express | 4.19.2 |
| Database | Firebase Admin (Realtime DB) | 12.2.0 |
| Cache | ioredis | 5.10.1 |
| Encryption | Node.js crypto (AES-256-CBC) | built-in |
| Module System | ES Modules (ESM) | ES2022 |

---

## Project Structure

```
gitcord/
├── src/
│   ├── commands/
│   │   ├── repo/
│   │   │   ├── create.js
│   │   │   ├── list.js
│   │   │   ├── info.js
│   │   │   ├── delete.js
│   │   │   ├── fork.js
│   │   │   ├── visibility.js
│   │   │   ├── rename.js
│   │   │   └── topics.js
│   │   ├── pr/
│   │   │   ├── create.js
│   │   │   ├── list.js
│   │   │   ├── view.js
│   │   │   ├── merge.js
│   │   │   ├── close.js
│   │   │   └── review.js
│   │   ├── issue/
│   │   │   ├── create.js
│   │   │   ├── list.js
│   │   │   ├── view.js
│   │   │   ├── close.js
│   │   │   └── assign.js
│   │   ├── release/
│   │   ├── gist/
│   │   ├── search/
│   │   ├── user/
│   │   ├── notify/
│   │   └── help.js
│   ├── events/
│   │   ├── ready.js
│   │   ├── interactionCreate.js
│   │   └── webhooks.js
│   ├── services/
│   │   ├── auth.js          # OAuth flow + token management
│   │   ├── github.js        # Octokit wrapper
│   │   ├── firebase.js      # DB client + encryption helpers
│   │   ├── redis.js         # Cache + rate limiting
│   │   └── logger.js        # Cross-guild activity logging
│   ├── utils/
│   │   ├── pagination.js    # Component V2 paginated embeds
│   │   ├── formatters.js    # Date, size, status formatters
│   │   └── constants.js
│   └── index.js             # Entry point
├── .env.example
└── package.json
```

---

## Environment Variables

```env
# Discord
DISCORD_TOKEN=           # Bot token from Discord Developer Portal
DISCORD_CLIENT_ID=       # Application / Client ID
DISCORD_GUILD_ID=        # Development guild ID (optional)

# GitHub OAuth
GITHUB_CLIENT_ID=        # OAuth App client ID
GITHUB_CLIENT_SECRET=    # OAuth App client secret
GITHUB_REDIRECT_URI=     # https://yourdomain.com/auth/github/callback

# Encryption
ENCRYPTION_KEY=          # 32-byte hex key for AES-256-CBC

# Firebase
FIREBASE_DATABASE_URL=   # https://your-project.firebaseio.com
FIREBASE_SERVICE_ACCOUNT= # Path to serviceAccountKey.json

# Redis
REDIS_URL=               # redis://localhost:6379
```

---

## Setup

### Prerequisites

- Node.js ≥18
- A Discord application with bot token ([Discord Developer Portal](https://discord.com/developers/applications))
- A GitHub OAuth App ([GitHub Developer Settings](https://github.com/settings/developers))
- Firebase project with Realtime Database enabled
- Redis instance

### Installation

```bash
# Clone the repository
git clone https://github.com/intruder0007/gitcord.git
cd gitcord

# Install dependencies
npm install

# Configure environment
cp .env.example .env
# Edit .env with your credentials

# Register slash commands
node src/deploy-commands.js

# Start the bot
node src/index.js
```

### OAuth Callback URL

Set the GitHub OAuth redirect URI to:

```
https://yourdomain.com/auth/github/callback
```

The Express server runs on port `3000` by default. In production, place it behind a reverse proxy (nginx / Caddy) with HTTPS.

---

## Security Model

```
┌─────────────────────────────────────────────────────────────────┐
│                        SECURITY LAYERS                          │
├─────────────────┬───────────────────────────────────────────────┤
│ Transport       │ HTTPS (OAuth callback), WSS (Discord gateway) │
├─────────────────┼───────────────────────────────────────────────┤
│ Token Storage   │ AES-256-CBC encrypted in Firebase RTDB        │
├─────────────────┼───────────────────────────────────────────────┤
│ Token Access    │ Per-user isolation — users only access their   │
│                 │ own encrypted token                            │
├─────────────────┼───────────────────────────────────────────────┤
│ OAuth State     │ CSRF-safe random state parameter per flow     │
├─────────────────┼───────────────────────────────────────────────┤
│ Rate Limiting   │ Redis-backed per-user rate limiter             │
├─────────────────┼───────────────────────────────────────────────┤
│ Scopes          │ Minimal GitHub scopes — only what each        │
│                 │ command category requires                      │
└─────────────────┴───────────────────────────────────────────────┘
```

---

## Logging System

```
Discord Server
└── #gitcord-logs (configured channel)
    ├── [REPO]     User created / deleted / forked repository
    ├── [PR]       Pull request opened / merged / closed
    ├── [ISSUE]    Issue created / closed / assigned
    ├── [RELEASE]  Release published / deleted
    ├── [AUTH]     Account linked / unlinked
    └── [ERROR]    Command execution failures
```

---

## Deployment

| Platform | Notes |
|----------|-------|
| Railway | `Procfile`: `node src/index.js` |
| Fly.io | `fly.toml` with `[http_service]` on port 3000 |
| VPS (Ubuntu) | PM2 process manager recommended |
| Docker | `FROM node:18-alpine` + copy + `npm ci` |

---

## Websit Documentation

The Gitcord marketing and documentation website is a separate Next.js project:

- **Framework**: Next.js 14 App Router with TypeScript
- **Styling**: Tailwind CSS v3 + liquid glass design system
- **Components**: shadcn/ui + custom React Bits animations
- **Docs**: 9 command categories, getting started guide, self-hosting docs
- **Features**: Real-time Discord presence (Lanyard WebSocket), animated hero, glass morphism UI

---

## License

Private project — all rights reserved. © 2025 JLAJ (intruder0007).
