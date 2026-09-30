# Dark Prague Workshop Resources

Bandwidth will be limited during the workshop. Install the tools and start these downloads early.

## Install

- Docker: https://docs.docker.com/get-started/get-docker/
- Node.js and npm: https://docs.npmjs.com/downloading-and-installing-node-js-and-npm/
- Git, only for `git clone` commands: https://git-scm.com/downloads

## Preload Early

Do this as early as possible. This is the largest shared download.

### 1. Pull Pubky Docker Images

Runs the local testnet and Homeserver.

- Repo: https://github.com/pubky/pubky-docker
- Docs: https://pubky.org/explore/technologies/pubky-docker/

```bash
git clone https://github.com/pubky/pubky-docker.git && cd pubky-docker && cp .env-sample .env
docker compose up homeserver -d
```

### 2. Download App Templates

```bash
npx tiged pubky/pubky-app-templates/basic-pubky-app my-pubky-app
(cd my-pubky-app && npm install)
```

The template already implements login & basic file operations. It can store private and public data.

Run it with `npm run dev`.

### 3. Sign In with the Pubky Ring Simulator

The simulator stands in for Pubky Ring during local development. It manages your test identity and authorizes your app, which receives a session without handling your identity's private key.

Keep the local testnet running, then:

1. Open your running app in the browser.
2. Under **Sign in with Pubky Ring**, click **Copy link**.
3. Open the [Pubky Ring Simulator](https://simulator.pubkyring.app/) in another tab.
4. If prompted, click **Prompt permission** and allow access to local services in your browser.
5. Select **Shortcut** and **paste** the copied link into **Auth link**. Pasting starts authentication automatically.
6. Return to your app. It signs in automatically once the simulator approves the request.

Use **Regular** mode when you want to create and select identities yourself before authorizing an app.

### 4. Check That Your App Works

Before changing the template, try saving and reading a file:

1. In your signed-in app, enter a **Title** and **Body**, then click **Create**.
2. Reload the app. You should still be signed in, and your file should appear in **Files**. Click **Edit** to check that its title and body were saved.
3. Copy the public key displayed in your app and open the [testnet Pubky Explorer](https://explorer.pubky.app/testnet/).
4. Allow access to local services if your browser asks. Paste your public key into Explorer and click **Explore**.
5. Browse to `/pub/template/files/` and open the JSON file. You should see the title and body you entered.

Your file is stored on your identity's Homeserver, and Explorer can read it independently of your app. These example files are public, so use sample data. Keep the local testnet running throughout this check.

Once this works, you have a working starting point for building your own app.

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

## Manual Development

Checkout this guide:

https://pubky.org/explore/pubky-protocol/getting-started/


## Resources

> More on https://pubky.org/resources/

Tools:

- https://explorer.pubky.app/testnet/ - Pubky Explorer to inspect the data on your homeserver.
- https://github.com/pubky/pubky-app-templates - App templates directory.

Websites:

- https://pubky.org - Main Pubky documentation and concepts.
- https://pubky.app - Social media platform built on Pubky and reference implementation.
- https://pubky.tech - Awesome list of Pubky projects, tools, and examples.
- https://pkdns.net — PKDNS public resolver

Github and packages:

- https://github.com/pubky/pubky-homeserver/ - Pubky SDK.
- https://www.npmjs.com/package/@synonymdev/pubky - JavaScript SDK package.
- https://crates.io/crates/pubky - Rust SDK crate.
- https://github.com/pubky/ - All Pubky repositories.

Other live Pubky apps for reference:

- https://uploadky.vercel.app/ - File sharing
- https://eventky.app - Event app built on Pubky.
- https://mapky.app - Map app built on Pubky.
- https://drive.pubky.app/ - Google Drive like Application
- https://mypubky.com - Pubky social/profile app.
- https://github.com/jvsena42/loopky - Flashcard Android App
