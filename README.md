# Dark Prague Workshop Resources

Bandwidth will be limited during the workshop. Install the tools and start these downloads early.

## Install

- Docker: https://docs.docker.com/get-started/get-docker/
- Node.js and npm: https://docs.npmjs.com/downloading-and-installing-node-js-and-npm/
- Git, only for `git clone` commands: https://git-scm.com/downloads

## Preload Early

### 1. Pull Pubky Docker Images

Runs the local testnet and Homeserver.

- Repo: https://github.com/pubky/pubky-docker
- Docs: https://pubky.org/explore/technologies/pubky-docker/

```bash
git clone https://github.com/pubky/pubky-docker.git && cd pubky-docker && cp .env-sample .env
docker compose up homeserver -d
```

Do this as early as possible. This is the largest shared download.

### 2. Download App Templates

```bash
npx tiged pubky/pubky-app-templates/basic-pubky-app my-pubky-app
(cd my-pubky-app && npm install)
```

The template already implements login & basic file operations. It can store private and public data.

Run it with `npm run dev`.

Use the Pubky Ring Simulator to manage your identity: https://simulator.pubkyring.app/


## AI Development

Best to use your AI agent to build a small app. For example:

```
This is an example app that provides login and file read/write. I want to turn this into a photo library. Propose how to do this. Feel free to ask clarifying questions.
```

Then add this small section to give your AI all the information it needs to build on Pubky:

```
Pubky: open protocol for key-based, censorship-resistant web apps. Public key identity, homeserver storage, Mainline DHT discovery over HTTP/REST.

Fetch the docs and help me build with Pubky:
- Full (~110k tokens): https://pubky.org/llms-full.txt
- Compact (~6k tokens): https://pubky.org/llms-small.txt
```

### Local Signer / Identity Manager

Identities / User Accounts are managed by a signer. Use the Pubky Ring simulator to create identities and authorize applications

https://simulator.pubkyring.app/

## Manual Development

Checkout this guide:

https://pubky.org/explore/pubky-protocol/getting-started/


## Resources

Tools:

- https://github.com/pubky/pubky-explorer - Pubky Explorer to inspect the data on your homeserver.
- https://github.com/pubky/pubky-app-templates - App templates directory.

Websites:

- https://pubky.org - Main Pubky documentation and concepts.
- https://pubky.app - Social media platform built on Pubky and reference implementation.
- https://pubky.tech - Awesome list of Pubky projects, tools, and examples.

Github and packages:

- https://github.com/pubky/pubky-homeserver/ - Pubky SDK.
- https://www.npmjs.com/package/@synonymdev/pubky - JavaScript SDK package.
- https://crates.io/crates/pubky - Rust SDK crate.
- https://github.com/pubky/ - All Pubky repositories.

Other live Pubky apps for reference:

- https://eventky.app - Event app built on Pubky.
- https://mapky.app - Map app built on Pubky.
- https://drive.pubky.app/ - Google Drive like Application
- https://mypubky.com - Pubky social/profile app.
