# Realm TTRPG suite

A suite of applications for facilitating the play and administration of
[tabletop roleplaying games](https://en.wikipedia.org/wiki/Tabletop_role-playing_game)

![banner](https://raw.githubusercontent.com/realm-ttrpg/.github/assets/banner.jpg)

- [🎉 MVP project board](https://github.com/orgs/realm-ttrpg/projects/1)
- [Prototype web application](https://realmttrpg.com)

## Architecture

### Diagram

![diagram](https://raw.githubusercontent.com/realm-ttrpg/.github/assets/architecture.jpg)

### Components

- **API Server** - The "brain". Responds to REST calls from the **Discord Bot** and the
  **Web Interface**. Uses the **Postgres Server** for storage. Communicates with the bot
  using RPC calls via the **Redis Server**. Also uses Redis for cache.
- **Discord bot** - Accepts commands and posts messages via Discord. Uses **SQLite** for
  storing Discord-related configuration. Communicates with the **API Server** directly or
  using RPC calls via the **Redis Server**. Also uses Redis for cache.
- **Web Interface** - The static web client. Communicates with the **API Server** using
  REST calls. Uses `localStorage` for cache (not pictured).
